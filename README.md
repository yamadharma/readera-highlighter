# Readera PDF Highlighter

Given an ebook and a ReadEra backup file, this script produces a PDF of the ebook with all your highlights and notes
you made in ReadEra. The PDF is is more portable and can be used in other programs, e.g. [Zotero](https://www.zotero.org/).

# Prerequisites

- Python
- `pip install --upgrade pymupdf`
- You also need [Calibre](https://calibre-ebook.com/) installed or at minimum ebook-convert on your PATH.

# Usage

First, you need the ReadEra backup file with your highlights. You can create it in the app:

- Go to Settings -> Synchronization, Backup & Restore
- Tap on "Create a backup"
- The new backup appears in the list of backups below. Tap on it and choose "Send", export it to where this script will be running, e.g. using Dropbox. This file has a name like `ReadEra-Premium_2024-02-18_12.57.bak` and will be read by this script. Place the ebook in the same directory, and run the script there as follows:

`python readera_pdf_highlighter.py make-highlighted-pdf YourBook.epub`

It will convert the ebook to PDF using Calibre and then add the highlights.

Other commands:

```
Usage: readera_pdf_highlighter.py <cmd> [args]
Commands:
  verify-citations-complete
    Checks all backup files in the current directory and shows which have all citations
  show-titles
    Show all books with citations
  show-citations <file or book title substring>
  make-highlighted-pdf <book_filename>
    Convert book to PDF and add highlights from ReadEra backup
```

In particular you can use `verify-citations-complete` if you have multiple ReadEra backup files and want to check which ones are complete/whether any are missing citations.

# Misc

- Zotera 6 is not able to show the highlights, but the upcoming Zotero 7 is (see [this issue](https://forums.zotero.org/discussion/105192/external-pdf-reader-highlights-not-recognized-in-zotero))
