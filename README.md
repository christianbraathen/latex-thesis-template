# latex-thesis-template


## A few notes to get you started if you're new to LaTeX

I suggest you first read this introduction: https://www.overleaf.com/learn/latex/Free_online_introduction_to_LaTeX_(part_2)

Furthermore, I suggest that you use Overleaf for your thesis. By paying a few dollars a month, you're able to have Google Doc functionality with your thesis partner. By clicking "Menu" in the upper-left corner of Overleaf, you can connect the thesis to Dropbox as well.

To get a better overview of the thesis, I structured the thesis in sections (see the `sections` folder). To add a new file to your thesis, add the file path to `main.tex`, like I do here with the front page: `\subfile{sections/01_introduction/0101_front_page}`. Then in the new file, add the following code snippet and start writing between the begin and end document code snippets:

```
\documentclass[../../main.tex]{subfiles}
\begin{document}

% WRITE HERE

\end{document}
```

To add comments that will not be compiled, use `%`. To get a literal percentage sign, use `\%`. Same goes for "&" (`\&`) and "$" (`\$`).

The following code snippet is found in `main.tex`and allows you to play around with headers and footers:

```
\usepackage{fancyhdr,lastpage}% http://ctan.org/pkg/{fancyhdr,graphicx,lastpage}
\fancypagestyle{plain}{
  \fancyhf{}% Clear header/footer
  \fancyfoot[C]{\thepage} % Right footer
}
```

I already added code to get proper line breaking in American–English. If you're writing in Norwegian, replace line 68–71 in `main.tex` with:

```
\usepackage[norsk]{babel}
\addto\captionsnorsk{%
  \renewcommand*{\indexname}{Indeks}
}
```

To add headings, you can use `\chapter{Title goes here}`, `\section{Subtitle goes here}`, `\subsection{Subsubtitle goes here}`, `\subsubsection{Subsubsubtitle goes here}`.

To add a figure, upload the file to the `images` folder and replace `nhh.jpg` in the code block below. Additionally, play around with the witdths of the captions and the images. And finally, remember to change the caption and the label.

```
\begin{figure}[H]
	\captionsetup{width=0.8\textwidth}
	\centering
	\includegraphics[width=0.20\textwidth]{images/nhh.jpg}
	\caption{skriv tittel her}
	\label{my-figure-label}
\end{figure}
```

The most important use of labels is for cross-references. By using `\ref{my-figure-label}` and `\pageref{my-figure-label}`, you will retrieve the figure number and the page of the figure. Example: "As we can see from Figure \ref{my-figure-label} on page \pageref{my-figure-label}, ..." would, for instance, give "As we can see from Figure 1 on page 29, ...". It's important to note that you should use a different label for each figure, table, section header, and so on.

To add a table, use tablesgenerator.com and switch the table style from "Default table style" to "Booktabs table style". To create a new table from scratch, you can for instance make the table data in Excel, then paste it in on the website through `File -> Paste table data...`. To edit an existing LaTeX table, paste it on the website through `File -> From LaTeX code...`. To move the table over to Overleaf, click "Generate", then "Copy to clipboard".

I have added three bibliography files (default setting I made was APA), which you can switch in `main.tex` if needed. You can perfectly use only one bibliography file, but I found it convenient to use three:

1. `bib_category_1.bib` is used for peer-reviewed references.
2.`bib_category_2.bib` is used for references that is not peer-reviewed but is still needed for your paper. Examples are numbers from the bureau of statistics, key newspaper articles, etc.
3.`bib_category_3.bib` is used for those references that you add for the time being but that you need to switch out before handing in your thesis. One example is Wikipedia entries. 

Adding references is quick and easy in LaTeX. For peer-reviewed articles, find the article on http://scholar.google.com, click the cite icon, click the BibTex link on the bottom of the modal window that pops up, copy the text, and paste it into `bib_category_1.bib`. For all other online references, install the "BibTex entry from URL" extension for Google Chrome. Please note that you will likely have to make some adjuments from this extension's output, but that is quick and easy.

Citing references is easy. The key is to get the citation tag, which is `uboe2017statistical` from the following example:

```
@article{uboe2017statistical,
  title={Statistical testing of bounded rationality with applications to the newsvendor model},
  author={Ub{\o}e, Jan and Andersson, Jonas and J{\"o}rnsten, Kurt and Lillest{\o}l, Jostein and Sandal, Leif},
  journal={European Journal of Operational Research},
  volume={259},
  number={1},
  pages={251--261},
  year={2017},
  publisher={Elsevier}
}
```

There are multiple formats you can get citations in-text. First add the reference above to the bibliography file, then play around with these code snippets to see the differences between them:

- `\textcite{uboe2017statistical}`
- `\citeauthor{uboe2017statistical}`
- `\cite{uboe2017statistical}`
- `\cite*{uboe2017statistical}`
- `\parencite{uboe2017statistical}`
- `\parencite*{uboe2017statistical}`


To have in-line quotations, use `\textquote{This is quote}`.


Writing math is one of LaTeX' biggest strengths. Here's an example, copy this code block into Overleaf and play around with it for yourself.

```
\begin{equation}
\begin{split}
Q = \frac{  \sum\limits_{i=1}^{n} p_0^i q_t^i }{ \sum\limits_{i=1}^{n} p_0^i q_0^i }
\end{split}
\end{equation}
```

To get a bullet-pointed list:

```
\begin{itemize}
\item These is a bullet point
\item This is another bullet point
\item etc
\end{itemize}
```

To get an enumerated list:

```
\begin{enumerate}
\item This is an enumerated point
\item This is another one
\item etc.
\end{enumerate}
```

## And a final tip

There's tons of other customizations you can do in LaTeX and I won't go through every detail here. Therefore: Google is your friend. Good luck!

P.S. If this template was useful for you, consider improving it here on GitHub so that others can benefit more.