
# Webpage2html

## Webpage2html: Save web page to a single html file

This is a simple script to save a web page to a single html file. No mhtml or pdf stuff, no xxx_files directory, just one single readable and editable html file.

The basic idea is to insert all css/javascript files into html directly, and use base64 data URI for image data.

## Usage and Example

save webpage directly from url(**recommended** way):

```bash
$ python webpage2html.py http://www.google.com > google.html
```

or save webpage first using browsers such as chrome, to something.html with something_files directory beside.

```bash
$ python webpage2html.py /path/to/something.html > something_single.html
```

But note that, the second method may not always work as expected, because there may be urls like `//ssl.gstatic.com/gb/images/v1_c69d5271.png` (from google index page), but the file is missing in `Google_files` directory saved by browsers.

Enable javascript, for example, save 2048 game page into a single html for offline playing

```bash
$ python webpage2html.py -s http://gabrielecirulli.github.io/2048/ > 2048.html
```

## Dependency

BeautifulSoup4, termcolor(optional)

```bash
$ pip install -r requirements.txt
```

or install them manually

```bash
$ pip install BeautifulSoup4 requests termcolor
```

The `termcolor` package is for colored log output support if you like.


For windows, you must `set PYTHONIOENCODING=utf-8` or use Python 3.6