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
import xlrd
from datetime import date


class ExcelTools(object):

    def __init__(self):
        self.excel_data = list()

    def get_excel_data(self, excel_path, sheet_name):
        wb = xlrd.open_workbook(excel_path)
        table = wb.sheet_by_name(sheet_name)

        colspan = {}
        if table.merged_cells:
            for item in table.merged_cells:
                for row in range(item[0], item[1]):
                    for col in range(item[2], item[3]):
                        if (row, col) != (item[0], item[2]):
                            colspan.update({(row, col): (item[0], item[2])})

        for i in range(table.nrows):
            tmp_data = []
            for j in range(table.ncols):
                if colspan.get((i, j)):
                    tmp_data.append(table.cell_value(*colspan.get((i, j))))
                else:
                    if table.cell(i, j).ctype == 3:
                        date_value = xlrd.xldate_as_tuple(table.cell_value(i, j), wb.datemode)
                        date_tmp = date(*date_value[:3]).strftime('%Y/%m/%d')
                        tmp_data.append(date_tmp)
                    else:
                        tmp_data.append(table.cell_value(i, j))
            self.excel_data.append(tuple(tmp_data))


if __name__ == '__main__':
    et = ExcelTools()
    et.get_excel_data("./test.xlsx", "Sheet1")
    print(et.excel_data)
    
```

