# my-latex-template
This repository contains commonly used LaTeX templates. The default compilers are `pdfLaTeX` and `BibTex`, or you can use the more convenient `LaTexmk` for compilation.

## Recommended File Structure
When writing a paper, it is recommended to use the following file structure for modular management. Use `\input{./main/xxx.tex}` in the main file `main.tex` to link each section. (See the code of each template for details)
```
ProjectMainFolder/
├── main.tex
├── main/
│   ├── introduction.tex
│   ├── preliminaries.tex
│   ├── methodology.tex
│   ├── ...
│   └── conclusion.tex
├── imgs/
│   ├── figure1.pdf
│   └── figure2.pdf
└── ref.bib
```
Most of the paper templates in this repository adopt the above structure. When changing templates for paper submission, you only need to change a small part of the code in `main.tex`.

## Mathematical Symbol System
This repository provides `notations.tex`, which predefines a series of commonly used shortcut symbol systems. This way, you don't have to frequently write long codes like `$\mathbf{X}$`, `\mathbb{R}`, `\mathcal{X}` in your paper.

The `notations.tex` in the template has already provided definitions for the following commonly used symbols:

### Bold Math:
Commonly used for matrix and vector symbols, written as
```[LaTeX]
$\w$, $\W$   # Suitable for most cases, just add a backslash before the letter
$\abf$       # Use \abf when \a is already occupied by the system
$\Tbf$       # \T is occupied by the transpose symbol, so use \Tbf
$\balpha$    # Add a b before Greek letters to bold them (only some of Greek letters are defined)
$\bfeta$     # The bold form of the Greek letter \eta is \bfeta, because it conflicts with \beta
$\onef$      # Bold 1, commonly used to define an all-ones vector
```
Effect:
```math
\boldsymbol{w}, \boldsymbol{W}, \boldsymbol{a}, \boldsymbol{\alpha}, \boldsymbol{\eta}, \boldsymbol{1}.
```

### Calligraphic Math
Commonly used to define sets, written as `$\Xc$`, `$\Sc$`, etc., i.e., add a lowercase c after the letter. Effect:
```math
\mathcal{X}, \mathcal{S}
```

### Blackboard Bold Math
Commonly used to define number fields and expectations, written as `$\Rb$`, `$\Eb$`, etc., i.e., add a lowercase b after the letter. Effect:
```math
\mathbb{R}, \mathbb{E}
```

### Special Symbols
- Transpose: Written as `$\T$`. For example, the effect of `$\A^\T$` is: $\boldsymbol{A}^\top$.
- Subject to: Written as `\sto`. For example, the effect of `$\sto a>0$` is: $\text{s.t. } a>0$.
- Trace of a matrix: Written as `\tr`. For example, the effect of `$\tr(\A)$` is: $Tr(\boldsymbol{A})$.
    Note: The definition of `\tr` is to support customizable trace symbol definitions, such as defining `\newcommand{\tr}{\mathsf{tr}}`, which results in a cooler looking $\mathsf{tr}(\boldsymbol{A})$.
- Other similar symbols include `\diag`, `\sign`, `\prox`, etc. Refer to `notations.tex` for details.