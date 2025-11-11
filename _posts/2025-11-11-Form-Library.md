---
layout: post
title: "Form Library"
subtitle: "In Python/LaTeX"
# cover-img: /assets/img/path.jpg
thumbnail-img: /assets/img/Form-Library/form-library-icon.png
share-img: /assets/img/Form-Library/form-library-icon.png
tags: [Job, Python, LaTeX, Project]
# author: Ricardo Kraft
---

During my two years at [MVZ Martinsried](https://www.medicover-diagnostics.de/genetische-beratung/unsere-beratungsstandorte/martinsried) as a working student, I mainly developed Python scripts for process automation and quality-of-life improvements. One project I’d like to highlight is a **Python library** I built for creating dynamic LaTeX-based forms, allowing fully formatted PDF documents to be generated with just a few lines of code.

## Example

> **I cannot share the source code directly, but I’ve included a censored example**  
> [📄 View on Google Drive](https://drive.google.com/file/d/1s_S31I-7FQmY48bJXQZ8CVvC3YVnmSVS/view?usp=sharing)

![Editor and Game Windows](/assets/img/Form-Library/example.png)


## How the Library Works

The library was structured around three main components:

1. **`example.tex`** - a LaTeX document defining the content structure.  
2. **`format.sty`** - a style file specifying standardized rules for fonts, colors, tables, headers, footers, images, table of contents etc..  
3. **`python methods`** - functions to dynamically insert data into the `.tex` file.

The workflow was designed to be **minimal and intuitive**:

- **1 line** to open the `template.tex`.  
- **1 line** to render it as a `.pdf`.  
- **1 line** to insert text, images, or tables.  

The library also supported logic for replacing placeholders in the LaTeX template with real data, making it easy to
fill the form via code.



