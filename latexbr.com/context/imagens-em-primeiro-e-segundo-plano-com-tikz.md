Imagens em primeiro e segundo plano com TikZ
============================================

Imagens em primeiro e segundo plano com TikZ
--------------------------------------------


Com o TikZ é possível inserir imagens em primeiro e segundo plano no LaTeX, para isso seguimos alguns passos:
Primeiro baixe duas imagens: [elefante-na-selva-dagua-ad0a9] em jpg e 
[elefante02_architetto_fr_01] em png com transparência.
Em seguida coloque-os na mesma pasta onde estará seu arquivo TeX. A partir daí é só digitar o código abaixo (Explicação nos comentários).

```latex
\documentclass[a4paper]{article}
\usepackage[utf8]{inputenc}
\usepackage{lipsum} %exemplo de texto
\usepackage{tikz}
\begin{document}
%remember picture: lembra a posição da figura.
%overlay: sobrepõe a figura em relação ao texto.
\begin{tikzpicture}[remember picture,overlay]
  %Opções de separação.
  \tikzset{inner sep=0pt,outer sep=0pt}
  %Plano de fundo (background)
  %Centralizado na página. Figura da altura do papel.
  \node at (current page.center {\includegraphics[height=\paperheight]{elefante-na-selva-dagua-ad0a9}};
\end{tikzpicture}

{\color{white}
Imagens em primeiro e segundo plano com TikZ
\lipsum[1-5]} %texto branco

\begin{tikzpicture}[remember picture,overlay]
  \tikzset{inner sep=0pt,outer sep=0pt}
  %Primeiro plano (foreground)
  %Nó posicionado acima e a esquerda do canto sul leste da página.
  \node[above left] at (current page.south east) {
    \includegraphics[width=10cm]{elefante02_architetto_fr_01}
  };
\end{tikzpicture}
\end{document}
```

Veja o resultado [aqui].

Lembre-se: a figura do primeiro plano deve ser em PNG e com transparência.
E observem um fato importante: a ordem em que as figuras são inseridas é que determinam sua posição, ou seja, inserimos primeiro a figura que queremos como plano de fundo. Depois o texto e só depois a figura de primeiro plano.

![image](http://2.bp.blogspot.com/_nn5BgloqIug/TT2ZFaA9cmI/AAAAAAAAAEk/1lvGkR-Jt-o/s400/back_foreground.jpg)

__PS__: Compile duas vezes pra ficar na posição correta.

Palavras-chave: primeiro plano com TikZ no LaTeX, plano de fundo com TikZ no LaTeX, foreground with TikZ with LaTeX, background with TikZ with LaTeX, figuras, imagens, dicas




[elefante-na-selva-dagua-ad0a9]:http://downloads.open4group.com/wallpapers/elefante-na-selva-dagua-ad0a9.jpg

[elefante02_architetto_fr_01]:http://www.public-domain-photos.com/free-cliparts-4/animals/mammals/elefante02_architetto_fr_01.png

[aqui]:http://www.4shared.com/file/5RNiIHEr/back_foreground.html?