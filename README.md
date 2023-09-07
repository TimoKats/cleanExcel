# Clean Excel
Library that parses and formats chaotic excel spreadsheets into a formatted numpy array or pandas dataframe.

### Installation
CleanExcel can be installed using the python package indexer. For this, you can run the command given below **or** install it through your IDE (like PyCharm). Note, CleanExcel was developed using Python 3.10 on Linux and has one external requirement (openpyxl). Hence, it's recommended to use this version at minimum. However, given the few requirements most Python versions/enviroments should work. 
```
pip3 install clean-excel
```

### Usage
CleanExcel is coded in a 'functional' manner. Meaning, you don't import classes. Instead, you import the functions you're interested in directly (less coding overhead). There are two functions you'll likely import. First, `load_excel(filename, tab, min_row=None, max_row=None, min_column=None, max_column=None, ignore=[])`. Second, `get_tabs(filename)`.  

The code snippet below shows how you can iterate through excel files and their tabs using CleanExcel. Note, if you don't know the tab names (or there's just one), you can set the value `tabs=None` in the import function. Then, it'll only import the first tab of each spreadsheet.

```Python
from cleanexcel import import_excel, get_tabs
import os # included in the standard library

data = []

for filename in os.listdir('test/'):
    tabs = get_tabs('test/' + filename) # get tabs function!
    for tab in tabs:
        data.append(import_excel('test/' + filename, tab)) # import excel function!
```

Next, the code snippet below shows you how you can only import one excel file without knowing (or being interested in) the tabs.

```Python
data = import_excel('filename.xlsx', tab=None)
```

### Convert to pandas 
CleanExcel doesn't automatically convert the processed data to a pandas dataframe (or numpy array). Instead, it returns a dictionary of lists where the keys are the entries and the values are lists of numbers (typically). Hence, if you want to convert it to a pandas dataframe, you can use the example from the following code snippet.

```Python
import pandas as pd
from cleanexcel import import_excel

data = import_excel('filename.xlsx', tab=None)
df = pd.DataFrame.from_dict(data)
```

## Support
[Donate](https://paypal.me/timokats)  
[Feedback](mailto:tpakats@gmail.com)  
[Pypi](https://pypi.org/project/clean-excel/)


