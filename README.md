# ZipSlipGen

## Description
ZipSlipGen can be used to create an archive file (zip, jar, tar, tar.bz2, tar.gz, or tgz) that contains files that have direcotry traversal characters in their filenames. Most commercial archive tools prevent the extraction of archives that have embedded files containing paths in their filenames, but many software development libraries are lacking the same protection mechanisms. If a program or library does not prevent/sanitize the directory traversal characters, ZipSlipGen can be used to generate zip files that will place a file at an arbitrary location on the target system once extracted.

## Requirements

* Python 3

## Usage

Run it like any othe Python script using ```-f``` to specify the file to include in the archive.

```
python zipslipgen.py -f <filename> [options]
```

By default, the ZipSlipGen produces an ```exploit.zip``` that has an embedded file with 8 directory traversal characters for Windows environment. Following options can be used to specify the wanted output:

```
-f, --filename          specify the file to include in the archive
-h, --help              show help
-o, --output            output archive's filename, format is taken from the file extension
-d, --depth             number of directories to traverse
-p, --path              path to add to embedded file's name after traversal characters
-os, --operating-system specify the target platform to use the correct traversal characters (unix/win)
```