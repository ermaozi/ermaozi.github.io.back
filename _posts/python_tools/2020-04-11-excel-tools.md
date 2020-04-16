---
layout: post 
title: 读取并查询Excel
categories: python小工具
description: Excel
keywords: Excel
typora-root-url: ../..
---

> 读取并查询Excel表中的数据

```python
# -*- coding:utf-8 -*-
import re

import xlrd


class ExcelTools(object):

    def __init__(self, full_file_path=None, sheet=None, title_index=1):
        """
        实例化查询对象
        :param full_file_path: Excel文件的绝对路径(str)
        :param sheet: sheet页的名称(str)或序号(int)
        :param title_index: 表头的行号(int)
        """
        if not full_file_path:
            full_file_path = ''
        self.data = xlrd.open_workbook(full_file_path)
        if isinstance(sheet, str):
            sheet_name = sheet if isinstance(sheet, str) else sheet
            self.table = self.data.sheet_by_name(sheet_name)
        else:
            sheet = sheet if sheet else 0
            self.table = self.data.sheets()[sheet]
        self.title_index = title_index - 1
        self.mergeJson = {}  # 合并单元格与该单元格的数据
        self.lld_data = []
        # 实例化时获取lld data, 防止以后多次获取
        self.get_lld_data()

    def get_lld_data(self):
        try:
            lists = self.table.merged_cells
            title = self.table.row_values(self.title_index)
            nrows = self.table.nrows  # 行数
            for i in range(1, nrows):
                rowValues = self.table.row_values(i)  # 某一行数据
                for idx, v in enumerate(rowValues):  # 某一行中列的数据
                    for mer in lists:  # 遍历合并单元格的列表  mer为元组
                        if (mer[0] <= i < mer[1]) and (mer[2] <= idx < mer[3]):  # 判断是否是合并行
                            # 处理合并行
                            if v != "":  # 不为空的合并值
                                self.mergeJson[mer] = v
            # 解析数据
            for i in range(self.title_index + 1, nrows):
                rowValues = self.table.row_values(i)  # 某一行数据
                event = {}
                for idx, v in enumerate(rowValues):  # 某一行中列的数据
                    if not title[idx]:
                        continue
                    # 去除值两边的空格
                    v = v.strip() if isinstance(v, str) else v
                    if self.mergeJson:
                        for tuplerc in self.mergeJson:  # data为字典  key 为元组   value  为该合并单元格的值
                            if (tuplerc[0] <= i < tuplerc[1]) and (tuplerc[2] <= idx < tuplerc[3]):  # 判断是否是合并行
                                if v == "":  # 不为空的合并值
                                    v = self.mergeJson[tuplerc]
                            else:
                                event[title[idx]] = v
                    else:
                        event[title[idx]] = v
                self.lld_data.append(event)
            return self.lld_data
        except Exception as ex:
            print(ex)

    def search_for_lld(self, serch_dic):
        """
        从Excel中获取指定条件的值
        :param serch_dic: {
                              condition: {'表头1': '对应的正则表达式1', 表头2: '对应的正则表达式2', ...},
                              result: ['期待返回表头1', '期待返回表头2', ...]
                          }
        :return: [
                     {'期待返回表头1': '对应值1-1', '期待返回表头2', '值1-2'},
                     {'期待返回表头1': '对应值2-1', '期待返回表头2', '值2-2'},
                     ...
                 ]
        """
        condition = serch_dic[u'condition']
        result_list = serch_dic.get(u'result', [])
        return_list = []
        # 遍历每一行
        for data in self.lld_data:
            flag = True
            ret_dic = {}
            for k, v in condition.items():
                value = data[k]
                sear = re.search(v, str(value))
                if not sear:  # v != data[k]:
                    flag = False
                    break
            if not flag:
                continue
            if not result_list:
                return_list.append(data)
                continue
            for k in result_list:
                ret_dic[k] = data[k]
            return_list.append(ret_dic)
        return return_list

    
```

