# TFLsTool
This is a toolkit related to TFL (Tables, Figures, and Listings) generation in the field of clinical biostatistics for pharmaceuticals

## Main Features
* `extract_shell_to_tracker()` extracting table types, table numbers, titles, and footnotes from DOCX format mock shells into a tracker, enabling statistical programmers to efficiently generate TFLs.

## Installation

```python
pip install TFLsTool
```

## Example
Enter the TFL path, extraction requirements, delimiter, document language, and output path, then run the program.
### Use in python
```python
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
### Use in SAS Viya
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

endsubmit;
run;
```
