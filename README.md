[![Not Maintained](https://img.shields.io/badge/Maintenance%20Level-Not%20Maintained-yellow.svg)](https://gist.github.com/cheerfulstoic/d107229326a01ff0f333a1d3476e068d)

# yarAnalyzer
Yara Rule Analyzer and Statistics

# Description
yarAnalyzer creates statistics on a yara rule set and files in a sample directory. Place some signatures with .yar extension in the "signatures" folder and then run yarAnalyzer on a certain sample directory like:

```yarAnalyzer.py -p /sample/path -s /signatures```

It will generate two tables as command line output and two CSV files. (yaranalyzer_file_stats.csv, yaranalyzer_rule_stats.csv)

A new feature is the inventory creation. 

```yarAnalyzer.py --inventory -s /signatures```

This will create a CSV file named ```yara-rule-inventory.csv``` (default, set with '-o') with information about the initialized rules. (Rule File;Rule Name;Description;Reference)

# Screenshots

Rule Statistics

![Rule Statistics](/screens/screen1.png)

File Statistics

![File Statistics](/screens/screen2.png)

CSV Output in Excel

![CSV Output in Excel](/screens/screen3.png)

# Usage

```
usage: yarAnalyzer.py [-h] [-p path] [-s sigpath] [-e ext] [-i identifier] 
                      [-m max-size] [-l max-string] [-f first-bytes] [-o output] 
                      [-t output-samples] [--excel] [--noempty] [--inventory] 
                      [--printAll] [--debug]

yarAnalyzer - Yara Rules Statistics and Analysis

options:
  -h, --help         show this help message and exit
  -p path            Path with samples files
  -s sigpath         Path to signature file(s)
  -e ext             signature extension
  -i identifier      Set an identifier - will be used in filename 
                     identifier_rule_stats.csv and identifier_file_stats.csv
  -m max-size        Max file size in MB (default=10)
  -l max-string      Max filename/rulename string length in command line output
  -f first-bytes     Number of first bytes to show in output
  -o output          Inventory output
  -t output-samples  Target directory to which samples without matches should be 
                     copied
  --excel            Add extras to suppress automatic conversion in Microsoft 
                     Excel
  --noempty          Don't show empty values
  --inventory        Create a YARA rule inventory only
  --printAll         Print all files that are scanned
  --debug            Debug output
  
```

# DO NOT

install the outdated "yara" Python module via pip. Use "yara-python" instead or install it from the github repo: [https://github.com/plusvic/yara-python](https://github.com/plusvic/yara-python)
