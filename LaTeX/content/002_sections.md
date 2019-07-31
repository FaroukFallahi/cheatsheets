# Sections
They are the way to divide documents into different logical partitions. They
are extremely easy to use though (unlike MS. word :D).

```latex
...
\begin{document}

\section{Introduction}
Some content here.
\subsection{Intro's first section}
Some other content.
\subsubsection{Intro's first section's first section!}
And some other stuff here.

\section{Related Work}
Reviewing other people's work on the matter.

\section{Our work}
Introducing and describing our work.

\section{Experiments}
Examining our work.

\section{Conclusion}
Last words here.

\end{document}
```

As you can see i have omitted the header section of the .tex file since it
would be way too much of repetition (because we have it in every cheatsheet).
Sections are auto-numbered and they can have subsections which themselves are
also auto-numbered. But sometime's we want sections without their number, to
get that we can use a * (star) to indicate that we don't need them:

```latex
\begin{document}

\section*{Not-numbered abstract}
Some content.

\section{Intro}
Some other content here.

\section*{Another not-numbered section in the middle}

\section{End}
Yet some other content.
\end{document}
```

