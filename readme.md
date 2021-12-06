# English-only tex template for IEICE conferences

## Introduction
This is an English-only tex template for IEICE conferecens, such as IE, MVE, etc.
If you
- want to use tex to write IEICE paper
- do not want to write Japanese title and abstract

then, this template is what you need.

## Usage
### VSCode with LaTeX Workshop
This part is the same as Japanese tex template, which requires `ptex2pdf` to compile. You can add the following settings in your `settings.json` file.
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

### Overleaf
If you want to use overleaf, the `latexmkrc` file is required. 

Ypu can see the template via this [link](https://www.overleaf.com/read/rsqzmxqkcwjg).

## Acknowledgement
On the official [website](https://www.ieice.org/jpn/kenkyuukai/shorui.html), only Japanese tex template is provided, as well as other formats (e.g., `*.docx`). 

In this repo, the source files are modified from the official documents.