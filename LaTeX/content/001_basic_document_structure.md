# Basic document structure
These are the most simple LaTeX examples (sort of like a hello world).

## A simple English article
```latex
\documentclass{article}

\title{Basic document structure}
\author{Mazhar Zandsalimi}

\begin{document}
\maketitle

\section{Introduction}
Section content comes here.
\subsection{Intro - subsection}
Subsection content comes here.
\subsubsection{Intro - subsubsection}
A subsection of the subsection.

\section{Conclusion}
Another section.

\end{document}
```

The `documentclass` specifies what type of a document we want to write (ex.
proc, book, etc.).

## A simple Persian (Arabic glyphs) article

```latex
\documentclass{article}

\usepackage{xepersian}
\settextfont[Scale=1.1]{XB Zar}
\setdigitfont{XB Zar}

\author{مظهر زندسلیمی}
\title{یک مثال ساده از لاتک}
\date{}

\begin{document}
\maketitle
اینجا محتویات قرار میگیرد.
\end{document}
```
