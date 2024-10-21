# my-latex-template
该仓库包含常用的 LaTeX 模板，默认的编译器是 `pdfLaTeX` 和 `BibTex`，
或者用更方便的 `LaTexmk` 也能进行编译.

## 推荐的文件结构
写论文时推荐用如下的文件结构以便模块化管理，
在主文件 `main.tex` 中使用 `\input{./main/xxx.tex}` 串联各节内容。（详见各模板的代码）
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
本仓库的大部分论文模板均采用如上结构。
在论文转投更换模板时，也只需要更换 `main.tex` 中少部分代码即可。

## 数学符号系统
本仓库提供 `notations.tex` 预定义了一系列常用的快捷符号系统。
这样你就无需在论文里经常写 `$\mathbf{X}$`、`\mathbb{R}`、`\mathcal{X}` 这样很长的代码。

模板中的 `notations.tex` 已经提供了如下常用符号的定义：

### 数学粗体：
常用于矩阵、向量符号，写法为
```[LaTeX]
$\w$, $\W$   # 大部分情况适用，反斜杠直接加字母
$\abf$       # 当 \a 已被系统占用时，使用 \abf
$\Tbf$       # \T 被转置符号占用，所以需要用 \Tbf
$\balpha$    # 部分希腊字母前加一个 b 加粗（只定义了常用的部分希腊字母）
$\bfeta$     # 希腊字母 \eta 的粗体是 \bfeta，因为和 \beta 冲突了
$\onef$      # 粗体的1，常用于定义全1向量
```
效果：
$$
\bm{w}, \bm{W}, \bm{a}, \bm{\alpha}, \bm{\eta}, \bm{1}.
$$

### 数学花体
常用于定义集合，写法为 `$\Xc$`、`$\Sc$` 等，即字母后面加小写c。效果：
$$
\mathcal{X}, \mathcal{S}
$$


### 数学板书粗体
常用于定义数域、期望，写法为 `$\Rb$`、`$\Eb$` 等，即字母后面加小写b。效果：
$$
\mathbb{R}, \mathbb{E}
$$


### 特殊符号
- 转置: 写法为 `$\T$`。例如 `$\A^\T$` 的效果为： $\bm{A}^\top$.
- 约束：写法为 `\sto`。例如 `$\sto a>0$`，效果为：$\text{s.t. } a>0$.
- 矩阵的迹：写法为 `\tr`。例如 `$\tr(\A)$` 的效果为： $Tr(\bm{A})$。
注：定义 `\tr` 是为了支持可修改迹的符号定义，例如定义 `\newcommand{\tr}{\mathsf{tr}}`，效果就是看起来更炫酷的 $\mathsf{tr}(\bm{A})$.
- 其它类似符号包括 `\diag`、`\sign`、`\prox` 等，参见 `notations.tex`。