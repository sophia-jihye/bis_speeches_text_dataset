# bis_speeches_text_dataset
Scraping Text Data of Central bankers' Speeches from bis.org 


## Introduction
Target webpage: https://www.bis.org/list/cbspeeches/from_01011997/index.htm   

## Folder structure
The following shows basic folder structure.
```
├── main.py 
├── config.py 
├── utils.py 
├── output
│   ├── pdf
│        ├── r970326a.pdf
│        ├── r970326b.pdf
│        ├── ...
│   ├── txt
│        ├── r970326a.txt
│        ├── r970326b.txt
│        ├── ...
│   ├── pkl
│        ├── bis_wo_content_dict__Jan-Mar 1997.pkl
│        ├── bis_wo_content_dict__Apr-jun 1997.pkl
│        ├── ...
│   ├── err
│        ├── web2pdf
│             ├── r970326b.log   # If an error occurrs while parsing data from web to .pdf, .log file is created.
│             ├── ...
│        ├── pdf2txt
│             ├── r970326c.log   # If an error occurrs while parsing data from .pdf to .txt, .log file is created.
│             ├── ...
│        ├── txt2csv
│             ├── r970326d.log   # If an error occurrs while parsing data from .txt to .csv, .log file is created.
│             ├── ...
│   ├── 19970101-00-59-59.log   # If an unexpecteed error orrcus, .log file is created.
│   ├── bis_w_content_FINAL.csv
│   ├── bis_w_content_FINAL.pkl

```

## Development Environment
* Ubuntu 16.04.6 LTS
* Python 3.6.9
* pdfminer 2.1.0
* beautifulsoup4 4.5.3
* requests 2.22.0
* argparse 1.4.0
* datetime 1.0.0
* numpy 1.15.4

## Usage
##### 0. To install pdfminer package, you need to install `pdfminer.six` via `pip` or `conda`. 
```sh
pip install -r requirements.txt 
```
or 
```sh
pip install pdfminer.six
```

##### 1. You can set the `sleep` time at `config.py`. 
```python
bis_sleep = 0.5  # YOU CAN EDIT THIS SLEEP TIME
```

##### 2. Run `main.py`.
```sh
python main.py --start_page_year 1997 --end_page_year 2019
```