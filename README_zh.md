# TFLsTool

这是一个用于制药临床生物统计领域的 TFL（表格、图形和列表）生成的工具包。

## 主要功能
* `extract_shell_to_tracker()` 功能用于从DOCX格式的shell模板中提取表格类型、表格编号、标题和脚注等信息，记录到一个tracker中，从而帮助统计程序员更高效地生成TFL（表格、图形和列表）。
* `completeness_report()`  功能用于从tracker.xlsx里提取P侧和Q侧的完成状态，并且根据状态作图发邮件。

## 示例

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

### completeness_report()

#### 在python解释器里这样用

```python
from TFLsTool import completeness_report

completeness_report(
    file_path='./tracker.xlsx',
    sheet_name='sheet',
    ds_select_list=['Type', 'SP', 'Pstatus', 'QC', 'Qstatus'],
    ds_status_list=['Ready', 'Complete'],
    project='Name of the project',
    side='all',

    email_sender = [
        'iamthesender@outlook.com',
        'thisispassword'
        ],
    email_recipient = ['12345678@outlook.com', '5211314@outlook.com'],
    email_cc = ['12345678@outlook.com', 'james@outlook.com'], 
    outpath='./output'
)
```
#### 在SAS Viya平台这样用

```SAS
proc python;
submit;

from TFLsTool import completeness_report
completeness_report(
    file_path='./tracker.xlsx',
    sheet_name='sheet',
    ds_select_list=['Type', 'SP', 'Pstatus', 'QC', 'Qstatus'],
    ds_status_list=['Ready', 'Complete'],
    project='Name of the project',
    side='all',

    email_sender = [
        'iamthesender@outlook.com',
        'thisispassword'
        ],
    email_recipient = ['12345678@outlook.com', '5211314@outlook.com'],
    email_cc = ['12345678@outlook.com', 'james@outlook.com'], 
    outpath='./output'
)

endsubmit;
run;
```

**其他语言版本: [English](README.md), [中文](README_zh.md).**
