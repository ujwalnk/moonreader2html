# moonreader2html

# What
A simple tool to convert you highlights from Moon+ Reader to a beautiful and portable HTML file.

# Why
Moon+ Reader is the most popular and the most customizable reader out there in the market, but getting your highlights out is next to impossible. This will help you convert it to a portable universal HTML format.


**Convert Moon+ Reader highlight export to readable HTML**

This utility makes it convert your highlights from [Moon+ Reader](https://play.google.com/store/apps/details?id=com.flyersoft.moonreaderp&hl=en&gl=US) into a single file HTML page.

## Installation
Clone this repository and install the python packages `jinja2` and `titlecase`.

## Usage
1. Open your book on Moon+ Reader say `Alice.epub` . Open the Chapters tab, go to the Bookmarks tab, click the share icon and choose the export to file from the menu.
2. This will generate a `Alice.mrexpt`, click on OK and save it on your phone, copy it over to a PC.
3. Get the book cover from the internet, it should of format `.png` and named `cover.png`
4.  Run this script:
```bash
python mrexpt2html.py Alice.mrexpt
```

- The Book name and Author might not be captured, to add them using the flags
```bash
python mrexpt2html.py Alice.mrexpt -a "Lewis Carroll"
```


# Here is a simple output of my highlights from Make Time

![[sample.png]]

### Options
**`debug`**
Turned on by default, and ensures that the book and file name are unique (by adding a timestamp). This is to allow multiple exports of the same book. This is convenient for testing this script or for having multiple reviews, but you can turn it off by following the below code: 
```bash
python ./mrexpt2html.py --debug=false my-book-highlights.mrexpt
```


**`titlecap`**
Turned on by default and converts chapter headings (highlights with notes like .h1/.h2/.h3) to *Title Cap* if they are *ALL CAPITAL* or *all lowercase*. This isn't specific to Moon+ Reader, but it's nice to be able to make this change - many books use ugly allcaps for chapter headings for typographical reasons but outside of the book formatting they're just not that nice. You can turn this off like this:

```bash
python ./mrexpt2html.py --titlecap=false my-book-highlights.mrexpt
```


**`author`**
Specify the author(s) which isn't available in the .mrexpt file. If unspecified the author is written as 'Unknown'.

---

Enjoy, let me know if there are any issues or suggestions by filing issues, and of course pull requests are very welcome.
