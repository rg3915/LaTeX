Cores
=====

Cores
-----


Conheça alguns pacotes que trabalham com cores no LaTeX. 
[xcolor] 
[dvipsnames]
[svgnames] 

Carregue o pacote 

```latex
\usepackage{xcolor} 
```

Para dvipsnames digite

```latex
\usepackage[dvipsnames]{xcolor}
```

![image](http://2.bp.blogspot.com/_nn5BgloqIug/TReFTpcu2AI/AAAAAAAAADU/FGz6zNzFJh8/s400/dvipsnames.png)

Para svgnames digite 

```latex
\usepackage[svgnames]{xcolor}
```

![image](http://2.bp.blogspot.com/_nn5BgloqIug/TReFb6XRF1I/AAAAAAAAADc/XcMom6DK15Y/s400/svgnames.png)

Saiba ainda como definir [novas cores] que variam de 0 a 1 em rgb (minúsculo) e de 0 a 255 em RGB (maiúsculo). 

Exemplo: 

```latex
%\definecolor{orange}{rgb}{1,0.5,0} ou 
\definecolor{orange}{RGB}{255,127,0}
```

Veja a seguir um exemplo simples e um outro com algumas cores do pacote: 

```latex
\documentclass{article} 
\usepackage[dvipsnames,svgnames,x11names]{xcolor} 
\usepackage{tikz} 
\usepackage[active,tightpage]{preview} 
\PreviewEnvironment{tikzpicture} 
\setlength\PreviewBorder{5pt}% 
\begin{document} 
\begin{tikzpicture}[font=\tiny]
%\definecolor{orange}{rgb}{1,0.5,0} ou 
 \definecolor{Orange}{RGB}{255,127,0} 
  \fill[yellow] (0,0) rectangle ++(1.5,1);
  \fill[Orange] (1.6,0) rectangle ++(1.5,1); %dvipsnames 
  \fill[OrangeRed] (3.2,0) rectangle ++(1.5,1); %svgnames 
  \fill[LightSkyBlue] (4.8,0) rectangle ++(1.5,1); %x11names 
  \node at (.75,1.2) {base color};
  \node at (2.35,1.2) {dvipsnames}; 
  \node at (4,1.2) {svgnames}; 
  \node at (5.6,1.2) {x11names}; 
  \node at (.75,.5) {yellow};
  \node at (2.35,.5) {Orange}; 
  \node at (4,.5) {OrangeRed}; 
  \node at (5.6,.5) {LightSkyBlue}; 
\end{tikzpicture}
\end{document}
```

![image](http://4.bp.blogspot.com/_nn5BgloqIug/TReEDBcyCnI/AAAAAAAAAC8/veQLN0NDyTE/s400/colors00.jpg)

```latex
\documentclass{article}
\usepackage[svgnames,dvipsnames,x11names]{xcolor} 
\usepackage{tikz} 
%\usetikzlibrary{calc} 
%recorta a figura 
\usepackage[active,tightpage]{preview} 
\PreviewEnvironment{tikzpicture} 
\begin{document}
\newcounter{x} %novo contador 
\setcounter{x}{1} %valor inicial do contador 
\newcounter{y} %novo contador 
\setcounter{y}{0} %valor inicial do contador 
\begin{tikzpicture} 
%Títulos 
 \foreach \ti in {base color,dvipsnames,svgnames,x11names} 
 { 
  \node at (\thex,1.5) {\ti}; 
  \pgfmathsetcounter{x}{\thex+2} %soma 1 no contador 
  \setcounter{x}{\thex} %redefine o contador 
 } 
%Cores 
 \foreach \cor in {blue,cyan,green,yellow,orange,red,magenta,purple} 
 { 
  \draw[fill=\cor] (0,-\they) rectangle ++(2,1) node[black,shift={(-1,-.5)}] {\cor}; 
  \pgfmathsetcounter{y}{\they+1} %soma 1 no contador 
  \setcounter{y}{\they} %redefine o contador 
 } 
\setcounter{y}{0}%reinicia contador 
 \foreach \cor in {BlueViolet,Aquamarine,GreenYellow,Goldenrod,Peach,RedOrange,Rhodamine,Purple}
 { 
  \draw[fill=\cor] (2,-\they) rectangle ++(2,1) node[black,shift={(-1,-.5)}] {\cor}; 
  \pgfmathsetcounter{y}{\they+1} 
  \setcounter{y}{\they} 
 } 
\setcounter{y}{0}%reinicia contador 
 \foreach \cor in {DarkBlue,LightBlue,LawnGreen,SandyBrown,Salmon,Crimson,Magenta,Purple} 
{ 
  \draw[fill=\cor] (4,-\they) rectangle ++(2,1) node[black,shift={(-1,-.5)}] {\cor}; 
  \pgfmathsetcounter{y}{\they+1} 
  \setcounter{y}{\they} 
 } 
\setcounter{y}{0}%reinicia contador 
 \foreach \cor in {Blue3,Cyan3,Green3,Yellow2,Orange2,Red3,Magenta2,Purple4} 
 { 
  \draw[fill=\cor] (6,-\they) rectangle ++(2,1) node[black,shift={(-1,-.5)}] {\cor}; 
  \pgfmathsetcounter{y}{\they+1} 
  \setcounter{y}{\they} 
 } 
\end{tikzpicture} 
\end{document}
```

![image](http://3.bp.blogspot.com/_nn5BgloqIug/TReEWSCISFI/AAAAAAAAADE/w2nIIXFoiI8/s400/colors01.jpg)

```latex
\documentclass{article} 
\usepackage{tikz} 
\usepackage[active,tightpage]{preview} 
\PreviewEnvironment{tikzpicture} 
\setlength\PreviewBorder{5pt}% 
\begin{document}
\pgfdeclareverticalshading{rainbow}{100bp}
{color(0bp)=(red); color(25bp)=(red); color(35bp)=(yellow); 
color(45bp)=(green); color(55bp)=(cyan); color(65bp)=(blue); 
color(75bp)=(violet); color(100bp)=(violet)} 
 \begin{tikzpicture}[shading=rainbow] 
  \shade[shading angle=90] (0,0) rectangle +(5,1); 
 \end{tikzpicture} 
\end{document}
```

![image](http://3.bp.blogspot.com/_nn5BgloqIug/TReEkOwJnZI/AAAAAAAAADM/HrL-olS0KUQ/s400/VisibleLightSpectrum.jpg)


[xcolor]:http://mirror.softwarelivre.ufsc.br/pub/ctan/macros/latex/contrib/xcolor/xcolor.pdf

[dvipsnames]:http://en.wikibooks.org/wiki/LaTeX/Colors

[svgnames]:http://en.wikibooks.org/wiki/LaTeX/Colors#Defining_new_colors

[novas cores]:http://en.wikibooks.org/wiki/LaTeX/Colors#Defining_new_colors