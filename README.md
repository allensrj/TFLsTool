# TFLsTool
This is a toolkit related to TFL (Tables, Figures, and Listings) generation in the field of clinical biostatistics for pharmaceuticals

## Main Features
* `extract_shell_to_tracker()` extracting table types, table numbers, titles, and footnotes from DOCX format mock shells into a tracker, enabling statistical programmers to efficiently generate TFLs.
* `completeness_report()` extract the completion status of the Production side and QC side from the tracker.xlsx, and then create graphs report based on the status and send emails. 
* `combine_rtf()` merge specified RTF documents in a defined order into a single RTF file.

# Installation

```python
pip install TFLsTool
```

## Change Log
### Date 2024/12/15
#### Added
* `combine_rtf()`, if addtoc='Y' and no tocfile provided, then generate a table of contents based on the merged RTF files.
### Date 2024/12/10
#### Added
* Introduced the `combine_rtf()` feature, enabling the merging of specified RTF documents in a defined order into a single RTF file.

# More information


**Read this in other languages: [English](README.md), [中文](README_zh.md).**

Document: https://tflstool.readthedocs.io/zh-cn/latest/