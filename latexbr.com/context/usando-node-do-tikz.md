Usando node do TikZ
===================

Usando node do TikZ
-------------------


Um grande e exclusivo recurso do TikZ é o uso de node (nó), um poderoso mecanismo que facilita e muito o trabalho com códigos complexos.
Como funciona um nó no TikZ? Para o Tikz nó é um ponto com nome e endereço, além disso ele pode ter uma forma, círculo ou retângulo, ou ficar invisível.
O nó é mais comumente usado para inserção de texto, mas veremos aqui que uma grande vantagem do uso de nó é que podemos usar seu endereço como referência para a construção de objetos em posição relativa ou [absoluta], por exemplo. Outra vantagem é que para desenhar uma curva unida por dois pontos sem se preocupar com seu endereço é muito mais simples com o uso de nós.
Veja um código simples:

```latex
\documentclass{article}
\usepackage{tikz}
\tikzset{%
>=latex, %melhor aparência para as setas
inner sep=0pt,outer sep=0pt, %sem separação entre os nós
}
\begin{document}
\begin{tikzpicture}
  \node[draw] (A) at (0,0) {retangulo}; %nó A
  \node[fill=red,circle] (B) at (4,2) {circulo}; %nó B
  \draw[->] (A) to[out=0,in=180] (B);
\end{tikzpicture}
\end{document}
```

![image](http://4.bp.blogspot.com/_nn5BgloqIug/TSJStm-9BwI/AAAAAAAAAD8/4MKVIltWKvk/s400/fig04.jpg)

Um exemplo de posição relativa:

```latex
\documentclass{article}
\usepackage{tikz}
\usetikzlibrary{positioning} %requer esta biblioteca
\tikzset{%
>=latex, %melhor aparência para as setas
inner sep=0pt,outer sep=0pt, %sem separação entre os nós
node distance=5mm %distância entre os nós
}
\begin{document}
\begin{tikzpicture}
  \node[draw] (A) at (0,0) {A}; %nó A
  \node[fill=cyan,circle] (B) at (1,0) {B}; %nó B
  \node[left=of A] {a esquerda de A}; %nó sem nome, apenas para inserir texto;
  \node[above=of B] {acima de B};
  \node[below=of B] {abaixo de B};
\end{tikzpicture}
\end{document}
```

![latex](http://4.bp.blogspot.com/_nn5BgloqIug/TSJS1Uki9BI/AAAAAAAAAEE/TffZzAMpbWU/s400/fig05.jpg)

Mais alguns exemplos do uso de nós em [Texample]: organogramas, esquema de árvores, etc.


[absoluta]:http://latexbr.blogspot.com/2011/01/trabalhando-com-posicao-absoluta-no.html

[Texample]:http://www.texample.net/tikz/examples/feature/node-positioning/