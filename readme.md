# English-only tex template for IEICE conferences

## Introduction
This is an English-only tex template for IEICE conferecens, such as IE, MVE, etc.
If you
- want to use tex to write IEICE paper
- do not want to write Japanese title and abstract

then, this template is what you need.

## Usage
This part is the same as Japanese tex template, which require `ptex2pdf` to compile. 

If you are using **VSCode** with **LaTeX Workshop**, you can add the following settings in your `settings.json` file.
```
"latex-workshop.latex.tools": [
    {
        "name": "ptex2pdf",
        "command": "ptex2pdf",
        "args": [
          "-l",
          "-ot",
          "-kanji=utf8 -synctex=1",
          "%DOC%"
      ]
    },
    {
        "name": "pbibtex",
        "command": "pbibtex",
        "args": [
          "%DOCFILE%",
          "-kanji=utf8"
        ]
    },
],
"latex-workshop.latex.recipes": [
    {
        "name": "ptex2pdf -> pbibtex -> ptex2pdf -> ptex2pdf",
        "tools": [
          "ptex2pdf",
          "pbibtex",
          "ptex2pdf",
          "ptex2pdf"
        ]
    }
],
```

## Acknowledgement
On the official [website](https://www.ieice.org/jpn/kenkyuukai/shorui.html), only Japanese tex template is provided, as well as other formats (e.g., `*.docx`). 

In this repo, the source files are modified from the official documents.