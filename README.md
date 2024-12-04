# monografia-tbbc

Thesis to qualify for the degree in Electronic Engineering and Telecommunications

<div align="center">

  <img id="last-update-badge" src="https://img.shields.io/badge/%F0%9F%93%85%20Last%20update%20-%20August%206%2C%202024-green.svg" alt="Last update: August 03, 2024" /> 
  <img src="https://img.shields.io/badge/MiKTeX--pdfTeX%204.19%20(MiKTeX%2024.3.31)-brightgreen.svg" alt="MiKTeX-pdfTeX 4.19 (MiKTeX 24.3.31)"/>
  <img src="https://img.shields.io/badge/Perl-5.32.1-blue.svg" alt="This is perl 5, version 32, subversion 1 (v5.32.1) built for MSWin32-x64-multi-thread"/>
</div>

# Table of Contents

- [monografia-tbbc](#monografia-tbbc)
- [Table of Contents](#table-of-contents)
- [Project Title](#project-title)
- [Description](#description)
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [Tests](#tests)
- [License](#license)
- [Contact](#contact)

## 🚀 Project Title

Thesis to qualify for the degree in Electronic Engineering and Telecommunications, about the development of a security process for identification and mitigation of vulnerabilities while working with node.js and express.js.

Title: Development of a replicable layered security process for web applications with Node.js: Identification and mitigation of common vulnerabilities.

Which is 'Desarrollo de un proceso replicable de seguridad en capas para aplicaciones web con Node.js: Identificación y mitigación de vulnerabilidades comunes'.

## 📄 Description

This repository contains the source code of the thesis to qualify for the degree in Electronic Engineering and Telecommunications.

The thesis is about the development of a security process for identification and mitigation of vulnerabilities while working with node.js and express.js.

## 🚀 Installation Requirements

This document was created using LaTeX, a high-quality typesetting system. To compile and edit the document, you will need to set up a LaTeX development environment. Follow the steps below to install the necessary tools:

1. **LaTeX Compiler**: Install [MiKTeX](https://miktex.org/download), a popular LaTeX distribution that includes a large collection of LaTeX packages and tools. MiKTeX is available for Windows, macOS, and Linux.

2. **Editor**: Download and install [TeXstudio](https://www.texstudio.org/), an integrated writing environment for creating LaTeX documents. TeXstudio offers numerous features like syntax-highlighting, integrated viewer, reference checking, and more, making it easier to work on complex LaTeX projects.

3. **VSCode Extension**: If you prefer Visual Studio Code (VSCode) as your editor, install the LaTeX Workshop extension. This extension provides rich functionality for LaTeX editing and compilation directly within VSCode, including preview, linting, and code completion.

4. **Perl Installation**: Install [Strawberry Perl](http://strawberryperl.com/) (for Windows users). Perl is required for the glossaries package, which is used to create glossaries and lists of acronyms, and for the Biber backend, a bibliography management tool for LaTeX.

5. **Biber Backend**: Ensure the Biber backend is installed and properly configured with your LaTeX distribution. Biber is used for bibliography management and is particularly suited for managing complex referencing schemes and Unicode data.

By installing these components, you will have a complete LaTeX environment set up for compiling and editing the document.

## For non-perl users

For non-perl users, the following texify toolchain from MikTeX may be worth a try:

```json
"latex-workshop.latex.recipes": [{
  "name": "texify",
  "tools": [
    "texify"
  ]
}],
"latex-workshop.latex.tools": [
  {
    "name": "texify",
    "command": "texify",
    "args": [
      "--synctex",
      "--pdf",
      "--tex-option=\"-interaction=nonstopmode\"",
      "--tex-option=\"-file-line-error\"",
      "--tex-option=\"-shell-escape\"",
      "%DOC_EXT%"
    ],
    "env": {}
  },
]
```

Refer to the non-perl user config [LaTeX Workshop documentation](https://github.com/James-Yu/LaTeX-Workshop/wiki/Compile#misc) for more information on setting up the LaTeX Workshop extension in VSCode.

## 🛠️ Tech Stack

<!-- - [![NodeJS.org][NodeJS.org]][NodeJS-url] -->

- [![strawberry-perl][strawberry-perl]][strawberry-perl-url]
- [![LaTex][LaTex]][LaTex-url]
- [![MiKTeX][MiKTeX]][MiKTeX-url]
- [![BibTeX][BibTeX]][BibTeX-url]
- [![Latex Workshop][Latex Workshop]][Latex Workshop-url]

## 📘 Usage

### Compiling the Paper

To compile the paper, follow these steps:

1. Open the `main.tex` file with TeXstudio.
2. Compile the file.
3. To compile with the list of acronyms, set the following recipe for the LaTeX workshop:

   ```json
   {
   	"name": "pdflatex, makeglossaries, pdflatex (2x)",
   	"tools": [
   		"pdflatex",
   		"makeglossaries",
   		"pdflatex",
   		"pdflatex",
   		"pdf windows"
   	]
   }
   ```

### Document Settings

- **Paper Margin**: Set with the `geometry` package in the preamble.
- **Paper Size**: `a4paper` (210mm x 297mm).
- **Font Size**: 12pt.
- **Line Spacing**: 1.5.

> Note: It's better to use the `a4paper` with the `geometry` package rather than the `documentclass` option for more flexibility. `letterpaper` is an option but is wider and shorter than `a4paper`.

### Language

- The paper is written in Spanish.
- The `babel` package is used to set the language for both the document and the bibliography.

### Structure

- **Chapters**: Each chapter is a different file located in the `chapters` folder. They are imported into the main file using the `\input` command.
- **Images**: Stored in the `images` folder in PNG format. Imported using the `\includegraphics` command.
- **Acronyms**: Listed in the `abbreviations.tex` file and imported using the `\input` command. The `glossaries` package with the `acronym` option is used. Printed with the `\printglossary` command.

### Bibliography

- **File**: `references.bib`.
- **Style**: IEEE, set with the `\bibliographystyle` command.
- **Package**: `biblatex` with `backend=biber` and `style=ieee`.
- **Citing**: References are cited in the text using the `\cite` command. Multiple keys can be separated by commas.

#### Example Reference

```bibtex
@article{key,
    author = {author},
    title = {title},
    journaltitle = {journaltitle},
    year = {year},
    volume = {volume},
    number = {number},
    pages = {pages},
    doi = {doi},
    url = {url},
}
```

## Synctex

The synctex is a tool that allows you to synchronize the source code with the pdf file. This is useful when you want to go to a certain part of the pdf file and you want to know where in the source code that part is. The synctex is enabled by default in the latex workshop extension.

From Code to PDF

- **Mac**: `Cmd` + `Option` + `J`
- **Windows/Linux**: `Ctrl` + `Alt` + `J`

From PDF to Code

- **Mac**: `Cmd` + Click
- **Windows/Linux**: `Ctrl` + Click

When making a copy of the pdf from the build folder to the root folder, the synctex is not working. To fix this, you need to copy the _.syntex.gz file from the build folder to the root folder. The _.syntex.gz file is a compressed file that contains the information needed to synchronize the source code with the pdf file. The \*.syntex.gz file is generated when you compile the document.

    {
        "name": "pdf windows",
        "command": "copy",
        "args": ["%OUTDIR_W32%\\%DOCFILE%.pdf", "%DIR_W32%\\"]
    },
    {
        "name": "synctex windows",
        "command": "copy",
        "args": ["%OUTDIR_W32%\\%DOCFILE%.synctex.gz", "%DIR_W32%\\"]
    },

And then you add it into the recipe in the latex workshop settings. The recipe is:

    {
        "name": "latexmk",
        "tools": ["latexmk", "pdf windows", "synctex windows"]
    },
    {
        "name": "pdflatex, makeglossaries, pdflatex (2x)",
        "tools": [
            "pdflatex",
            "makeglossaries",
            "pdflatex",
            "pdflatex",
            "pdf windows",
            "synctex windows"
        ]
    },

## Vscode Settings

To avoid seeing the aux files in the explorer, you can add the following to the settings.json file:

    "files.exclude": {
    	"node_modules/": true,
    	"build/main.*": true,
    },

## Contributing

...

## Tests

...

## License

MIT License - see the [LICENSE](LICENSE) file for details

## Contact

...

[NodeJS.org]: https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white "NodeJS.org"
[NodeJS-url]: https://nodejs.org/es/ "NodeJS.org"
[Docker.com]: https://img.shields.io/badge/Docker-2CA5E0?style=for-the-badge&logo=docker&logoColor=white "Docker.com"
[Docker-url]: https://www.docker.com/ "Docker.com"
[ExpressJS.com]: https://img.shields.io/badge/Express.js-404D59?style=for-the-badge "ExpressJS.com"
[ExpressJS-url]: https://expressjs.com/ "ExpressJS.com"
[JWT.io]: https://img.shields.io/badge/JSON%20Web%20Tokens-000000?style=for-the-badge&logo=json-web-tokens&logoColor=white "JWT.io"
[JWT-url]: https://jwt.io/ "JWT.io"
[PassportJS.com]: https://img.shields.io/badge/Passport.js-34E27A?style=for-the-badge&logo=passport&logoColor=white "PassportJS.com"
[PassportJS-url]: http://www.passportjs.org/ "PassportJS.com"
[strawberry-perl]: https://img.shields.io/badge/Strawberry%20Perl-8A2BE2?style=for-the-badge&logo=perl&logoColor=white "Strawberry Perl"
[strawberry-perl-url]: http://strawberryperl.com/ "Strawberry Perl"
[LaTex]: https://img.shields.io/badge/LaTeX-008080?style=for-the-badge&logo=latex&logoColor=white "LaTex"
[LaTex-url]: https://www.latex-project.org/ "LaTex"
[MiKTeX]: https://img.shields.io/badge/MiKTeX-008080?style=for-the-badge&logo=latex&logoColor=white "MiKTeX"
[MiKTeX-url]: https://miktex.org/ "MiKTeX"
[BibTeX]: https://img.shields.io/badge/BibTeX-008080?style=for-the-badge&logo=latex&logoColor=white "BibTeX"
[BibTeX-url]: https://www.bibtex.com/ "BibTeX"
[Latex Workshop]: https://img.shields.io/badge/LaTeX%20Workshop-008080?style=for-the-badge&logo=latex&logoColor=white "Latex Workshop"
[Latex Workshop-url]: https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop "Latex Workshop"
