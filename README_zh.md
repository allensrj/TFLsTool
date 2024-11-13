# TFLsTool

这是一个用于制药临床生物统计领域的 TFL（表格、图形和列表）生成的工具包。

## 主要功能

 功能用于从DOCX格式的shell模板中提取表格类型、表格编号、标题和脚注等信息，记录到一个tracker中，从而帮助统计程序员更高效地生成TFL（表格、图形和列表）。

## 示例

输入提取路径、提取的条件参数、分隔符类型、语言类型、输出路径，然后运行程序。

### extract_shell_to_tracker()

#### 在python解释器里这样用

```python
from TFLsTool import extract_shell_to_tracker

extract_shell_to_tracker(table_path='./project-table.docx',
table_conditions_list=[["Table", re.compile(r'\d'), '.']],

listing_path='./project-listings.docx',
listing_conditions_list=[["Listing", re.compile(r'\d'), '.']],

figure_path='./project-figures.docx',
figure_conditions_list=[["Figures", re.compile(r'\d'), '.']],

title_split='\n',
language='EN',
output_path='./tracker_results.xlsx'
)
```
#### 在SAS Viya平台这样用

```SAS
proc python;
submit;

from TFLsTool import extract_shell_to_tracker
extract_shell_to_tracker(
    table_path='./project-table.docx',
    table_conditions_list=[["Table", re.compile(r'\d'), '.']],
    
    listing_path='./project-listings.docx',
    listing_conditions_list=[["Listing", re.compile(r'\d'), '.']],
    
    figure_path='./project-figures.docx',
    figure_conditions_list=[["Figures", re.compile(r'\d'), '.']],

    title_split='\n',
    language='EN',
    output_path='./tracker_results.xlsx'
)
```

**其他语言版本: [English](README.md), [中文](README_zh.md).**
