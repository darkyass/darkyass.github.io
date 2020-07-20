<!-- .slide: data-background="#000000" -->
# Latex: <br> Éditer en Arabe



<!-- .slide: data-background="#000000" -->
# Choix du package Latex de support


## Package Latex Polyglossia

* <a href="https://ctan.org/pkg/polyglossia" target="_blank">Polyglossia</a>: package Latex de traitement de textes multilingues pour compilation XeLaTeX.


## Package Latex Babel
* <a href="https://www.ctan.org/pkg/babel" target="_blank">Babel</a>: package Latex de traitement de textes multilingues pour compilation PdfLaTeX.



<!-- .slide: data-background="#000000" -->
# Exemples de documents


## En utilisant <br> le package Polyglossia

```latex
% !TEX TS-program = XeLaTeX

\documentclass{article}

\usepackage{geometry}
\geometry{hmargin=1.5cm,vmargin=1.5cm}

\usepackage{amsmath,amsfonts,amssymb,fourier}

\usepackage{fontspec}
\setmainfont{Times New Roman}
\setsansfont{Arial}
\newfontfamily\arabicfont[Scale=1.15,Script=Arabic]{Amiri}
\newfontfamily\arabicfontsf[Scale=1.15,Script=Arabic]{Amiri}
\usepackage{polyglossia}
\setdefaultlanguage[locale=morocco]{arabic}

\addto\captionsarabic{ 
  \renewcommand{\contentsname}{محتوى الدرس}
}
\usepackage{tocloft}
\renewcommand{\cftsecleader}{\cftdotfill{\cftdotsep}}

\begin{document}
\tableofcontents{}

\clearpage

\section{المحور الأول}
\subsection{الجزء الأول}
نص باللغة العربية
\beginL
Texte en français
\endL

\subsection{الجزء الثاني}
عبارة رياضية
$\lim\limits_{x\to+\infty}f(x)=1$

\section{المحور الثاني}
\subsection{الجزء الأول}
\subsection{الجزء الثاني}
\end{document}
```
Voir le résultat de la compilation sur <a href="https://www.overleaf.com/read/bsrnyrmbbhgd" target="_blank">Overleaf</a>.


## En utilisant <br> le package babel

```latex
% !TEX TS-program = pdflaTeX

\documentclass{article}
\usepackage[utf8]{inputenc}
\usepackage[LFE,LAE]{fontenc}
\usepackage[french,arabic]{babel}
\frenchsetup{SuppressWarning}

\usepackage{etoolbox}
\renewcommand \thesection {\textLR{\arabic{section}}}
\renewcommand \thesubsection {\thesection.\textLR{\arabic{subsection}}}
\renewcommand \thepage {\textLR{\arabic{page}}}

\begin{document}
\selectlanguage{arabic}
\tableofcontents{}

\clearpage

\section{المحور الأول}
\subsection{الجزء الأول}
نص باللغة العربية
\textLR{
  Texte en français
}

\subsection{الجزء الثاني}
عبارة رياضية
$\lim\limits_{x\to+\infty}f(x)=1$

\section{المحور الثاني}
\subsection{الجزء الأول}
\subsection{الجزء الثاني}
\end{document}
```
Voir le résultat de la compilation sur <a href="https://www.overleaf.com/read/vdyydvgjhfcx" target="_blank">Overleaf</a>.



<!-- .slide: data-background="#000000" -->
# Fin

<!--- ![External Image](https://s3.amazonaws.com/static.slid.es/logo/v2/slides-symbol-512x512.png) -->
