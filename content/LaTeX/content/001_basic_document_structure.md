# Basic document structure
These are the most simple LaTeX examples (sort of like a hello world).

## A simple English article
```latex
\documentclass{article}

\title{Basic document structure}
\author{Mazhar Zandsalimi}

\begin{document}
\maketitle
Here comes the content of our document.
\end{document}
```

The `documentclass` specifies what type of a document we want to write (ex.
proc, book, etc.). To compile, we use `pdflatex file.tex` and then a pdf will
be created for us! It's that easy.

## A simple Persian (Arabic glyphs) article

```latex
\documentclass{article}

\usepackage{xepersian}
\settextfont[Scale=1.1]{Vazir}
\setdigitfont{Vazir}

\author{مظهر زندسلیمی}
\title{یک مثال ساده از لاتک}
\date{}

\begin{document}
\maketitle
اینجا محتویات قرار میگیرد.
\end{document}
```

Obviously, you need to download a Persian font to be running this example. Also
we need to compile the document using `xelatex file.tex` instead. If you are
planning to use a LaTeX helper (like texstudio) then all you need to do is to
change the compile type to XeLaTeX.
