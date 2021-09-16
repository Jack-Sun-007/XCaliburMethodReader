# Thermo XCalibur Method File Reader  .meth方法文件查看

A simple command-line program for mass spectrometry researchers that extracts and converts data from Thermo XCalibur Method (.meth) files.

一个简单的命令行程序，能够从Thermo XCalibur Method (.meth) 文件中提取数据

Uses the [olefile](https://olefile.readthedocs.io/en/latest/Howto.html) Python package to extract the data.

使用 [olefile](https://olefile.readthedocs.io/en/latest/Howto.html) Python 包提取数据

## Usage  用法

Help Text:

帮助
```
>>> python XCaliburMethodReader.py --help

usage: XCaliburMethodReader.py [-h] [-s STREAM] [--to {text,xml,json}]
                               [--output OUTPUT]
                               FILENAME

Extracts and converts data from Thermo XCalibur Method (.meth) files.

positional arguments:
  FILENAME              The Thermo XCaliber .meth file to read.

optional arguments:
  -h, --help            show this help message and exit
  -s STREAM, --stream STREAM
                        the data source you want to view (e.g. "Thermo
                        Exactive")
  --to {text,xml,json}  the data type to convert to.
  --output OUTPUT, -o OUTPUT
                        File to save data into, if desired.


```

Print File's Directory:

输出.meth方法文件里所包含的目录
```bash
>>> python XCaliburMethodReader.py HelaStandard120.meth

Proxeon_EASY-nLC
LCQ Header
AuditData
Thermo Exactive
```

Pretty-Print Data

输出方法数据
```bash
>>> python XCaliburMethodReader.py HelaStandard120.meth -s "Thermo Exactive"

                           Method of Q Exactive HF-X

OVERALL METHOD SETTINGS

Global Settings
Use lock masses                                                         best
Lock mass injection                                                        ―
Chrom. peak width (FWHM)                                                  15 s
Time
Method duration                                                       120.00 min
...
```

