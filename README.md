# Clean Excel
Library that parses and formats chaotic excel spreadsheets into a formatted numpy array or pandas dataframe.

### Installation
CleanExcel can be installed using the python package indexer. For this, you can run the command given below **or** install it through your IDE (like PyCharm). Note, CleanExcel was developed using Python 3.10 on Linux and has one external requirement (openpyxl). Hence, it's recommended to use this version at minimum. However, given the few requirements most Python versions/enviroments should work. 
```
pip3 install clean-excel
```

### Usage
CleanExcel is coded in a 'functional' manner. Meaning, you don't import classes. Instead, you import the functions you're interested in directly (less coding overhead). There are two functions you'll likely import. First, `load_excel(filename, tab, min_row=None, max_row=None, min_column=None, max_column=None, ignore=[])`. Second, `get_tabs(filename)`.  

The code snippet below shows how you can iterate through excel files and their tabs using CleanExcel. Note, if you don't know the tab names (or there's just one), you can set the value `tabs=None` in the import functions. Then, it'll only import the first tab of each spreadsheet.

```Python

```
