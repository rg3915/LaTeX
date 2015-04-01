Figura/tabela em uma coluna num documento de duas ou mais colunas
=================================================================

Figura/tabela em uma coluna num documento de duas ou mais colunas
-----------------------------------------------------------------

Já vimos no post [inserindo figuras no LaTeX] e [posicionando figuras com TikZ] como inserir figuras no LaTeX, inclusive em duas colunas e subfiguras.
Veremos agora como inserir uma figura, num documento de duas ou mais colunas, de forma que a figura ocupe a largura da página.
Vejamos o resultado para uma figura num documento de três colunas.

![imagem](http://3.bp.blogspot.com/--HKoMvUN360/UHtNEDY57VI/AAAAAAAAAjo/ACFBfTAaMEE/s400/figura_duas_colunas01.png)

Eis o código:
```latex
\documentclass[a4paper]{article}
\usepackage{multicol, blindtext, graphicx}
\usepackage[brazil]{babel}
\begin{document}
\begin{multicols}{3}

\begin{figure*}[ht]
    \centering
    \includegraphics[width=\linewidth]{joaninha}
    \caption{Figura de uma coluna num documento de v\'arias colunas.}
\end{figure*}

\Blindtext

\begin{table*}[ht]
    \centering
    \begin{tabular}
    {p{0.15\linewidth}p{0.15\linewidth}p{0.15\linewidth}p{0.15\linewidth}p{0.15\linewidth}}
        \hline
        coluna 1 & coluna 2 & coluna 3 & coluna 4 & coluna 5\\
        \hline
        1 & 2 & 3 & 4 & 5\\
        6 & 7 & 8 & 9& 10\\
        11 & 12 & 13 & 14 & 15\\
        16 & 17 & 18 & 19 & 20\\
        21 & 22 & 23 & 24 & 25\\
        \hline
    \end{tabular}
    \caption{Tabela de uma coluna num documento de v\'arias colunas.}
\end{table*}

\Blindtext

\end{multicols}
\end{document}
```

Veja também a tabela.

![image](http://4.bp.blogspot.com/-_Z2csE9mV5A/UHtNE4CfoGI/AAAAAAAAAjw/IGJfTF6Q1Sk/s400/figura_duas_colunas02.png)


[inserindo figuras no LaTeX]:http://latexbr.blogspot.com.br/2011/07/inserindo-figuras-no-latex.html
[posicionando figuras com TikZ]: http://latexbr.blogspot.com.br/2011/07/posicionando-figuras-com-tikz.html