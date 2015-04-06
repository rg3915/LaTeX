Trabalhando com posição absoluta no TikZ
========================================

Trabalhando com posição absoluta no TikZ
----------------------------------------


Este é certamente o grande diferencial do TikZ. Trabalhando com posição absoluta é possível se desenhar qualquer coisa em qualquer posição da página. É como se você abrisse um editor de imagens e desenhasse onde quiser.
Veja em [PGF manual CVS 2010] página 199.
Veja um código simples:

```latex
\begin{tikzpicture}[remember picture,overlay]
\node (A) at (current page.center) {}; %nó no centro da página
\draw (A) circle (2cm);
\node (B) at (current page.south west) {Texto no canto inferior esquerdo};
\end{tikzpicture}
```

O uso de (current page.center) posiciona o nó no centro da página. A opção remember picture grava a posição da figura atual para que a mesma possa ser usada posteriormente. A opção overlay permite que a figura fique em primeiro plano, sobrepondo o texto da página, caso haja.

Veja um exemplo mais completo que pode ser baixado [aqui].

```latex
\documentclass{article}
\usepackage{tikz}
\usepackage{lipsum} %texto em latim
\begin{document}
%definição da caixa: preenchimento amarelo, cantos arredondados, separação interna, largura do texto, posicionado acima e a direita do nó.
\tikzstyle{caixa} = [fill=yellow!50,rounded corners=5mm,inner sep=2mm,text width=4cm,above right]
\begin{tikzpicture}[remember picture,overlay]
\node (A) at (current page.center) {}; %nó no centro da página
\draw (A) circle (2cm);
\node[caixa] (B) at (current page.south west) {
Texto no canto inferior esquerdo com algumas configuracoes definidas por \tikzstyle.
};
\end{tikzpicture}
\lipsum[1-5] %texto em latim
\end{document}
```


![image](http://3.bp.blogspot.com/_nn5BgloqIug/TUKcdcU1pUI/AAAAAAAAAE0/x1aEDxudYwY/s320/posicao.jpg)




[PGF manual CVS 2010]:http://media.texample.net/pgf/builds/pgfmanualCVS2010-09-28.pdf

[aqui]:http://www.4shared.com/file/CgzpW-xL/posicao.html