# TFLsTool

这是一个用于制药临床生物统计领域的 TFL（表格、图形和列表）生成的工具包。

## 主要功能
* `extract_shell_to_tracker()` 功能用于从DOCX格式的shell模板中提取表格类型、表格编号、标题和脚注等信息，记录到一个tracker中，从而帮助统计程序员生成TFL（表格、图形和列表）。
* `completeness_report()`  功能用于从tracker.xlsx里提取P侧和Q侧的完成状态，并且根据状态作图发邮件。
* `combine_rtf()` 功能用于按照指定顺序合并RTF文档到一个RTF文件中。

## 安装

```python
pip install TFLsTool
```

你可以在python解释器或SAS Viya平台中使用这个库。

## 更新日志
### Date 2024/12/10
#### Added
* 添加了 `combine_rtf()` 功能。


**其他语言版本: [English](README.md), [中文](README_zh.md).**

文档： https://tflstool.readthedocs.io/zh-cn/latest/