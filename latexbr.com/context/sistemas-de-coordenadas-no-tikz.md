Sistemas de coordenadas no TikZ
===============================

Sistemas de coordenadas no TikZ
-------------------------------


O [TikZ] trabalha com dois sistemas de coordenadas: [retangulares] e [polares]. Abordaremos aqui algumas formas de se desenhar figuras no TikZ usando essas coordenadas na sua posição absoluta e relativa.

#####Coordenadas Retangulares

Um sistema de [coordenadas retangulares] ou [coordenadas cartesianas no plano] consiste de um par ordenado (x,y) onde x é a entrada referente ao eixo horizontal e y é a entrada referente ao eixo vertical do [plano cartesiano].

![image](http://4.bp.blogspot.com/-LZzRYQd6pIM/TeSEE55ANFI/AAAAAAAAAIs/oCP2-JZfFvM/s1600/figplano01.png)

No [TikZ] vamos interpretar em primeiro momento como coordenadas retangulares em __posição absoluta__, visto que depois reveremos um pequena variação deste item.
Em TikZ as coordenadas retangulares são expressas da mesma forma como a conhecemos nas notações matemáticas, entre parênteses: (x,y)
As entradas x e y aceitam qualquer valor real.

__Obs__: Por padrão a unidade de medida do TikZ é cm. Mas o TikZ aceita mm, pt (ponto) 1cm = 28.45 pt, in (polegada) 1in = 25.4 mm, etc.

Vejamos alguns exemplos:
__Exemplo 1__: ponto
Vamos desenhar um ponto na coordenada (2,1), para isso digite:
```latex
\fill[blue] (2,1) circle (1mm) node[above right] {$P_1$};
```

O trecho node[above right] {$P_1$} é para inserir uma legenda no ponto.

![image](http://3.bp.blogspot.com/-5erPFlD3NPM/TeSESRMI10I/AAAAAAAAAIw/qE-bpqTwvMo/s320/figCRet01.png)

Note que o ponto de __origem__ no sistema de coordenadas retangulares em __posição absoluta__ é o ponto (0,0).

__Exemplo 2__: reta
Para desenhar uma reta precisamos de pelo menos dois pontos.
```latex
\draw[->,blue] (0,0) -- (2,1);
```

Uma reta saindo da origem e indo até o ponto (2,1).

[image](http://2.bp.blogspot.com/-WSinkkQw3Yc/TeSFBLPA_FI/AAAAAAAAAI0/mVlXIJLJGQ8/s320/figCRet02.png)

__Exemplo 3__: retângulo
Veja no código a seguir que as coordenadas de um retângulo são dadas pelos pontos P1 e P2.
```latex
\draw[blue] (1,1) rectangle (4,3);
```

![image](http://4.bp.blogspot.com/-UQVU3ZvGXRM/TeSFGgetsDI/AAAAAAAAAI4/BNW7L4fKPdg/s320/figCRet03.png)

#####Coordenadas Relativas

As __coordenadas relativas__ funcionam da seguinte forma: dado um ponto fixo (a,b) em coordenadas absolutas o ponto (x,y), em __coordenadas relativas__, é dado por:

![image](http://2.bp.blogspot.com/-LhpA2yy60r8/TeSBrueuL8I/AAAAAAAAAIo/yAzV4HRzJy4/s1600/eq01.gif)

ou (x,y)=(a,b)+(x1,y1).
Ou seja, (a,b) é a __nova origem__ no sistema de coordenadas relativas e (x1,y1) é o ponto que deve ser "somado" à nova origem para se obter o novo ponto (x,y).

![image](http://2.bp.blogspot.com/-nOewq9MeiHs/TeSFNISA6eI/AAAAAAAAAI8/62a0H1OUFlY/s320/figplano02.png)

__Exemplo 4: ponto__
```latex
\fill (2,1) circle (1mm) node[below left] {O};
\fill[blue] (2,1)+(1,1) circle (1mm) node[above right] {$P_1$};
```

[image](http://4.bp.blogspot.com/-60EmGZ2MxwQ/TeSFTDuV2GI/AAAAAAAAAJA/9QmvBCa0lrY/s320/figCRel01.png)

Repare que o ponto (2,1) é a nova origem e (1,1) é o ponto que somado à nova origem resulta no ponto (3,2).

__Exemplo 5: reta__
Escreva o código a seguir:
\draw[->,blue] (2,1) -- +(2,1);

Comparando com a reta desenhada anteriormente a única diferença é que agora a nova origem é o ponto (2,1) e a reta vai até o ponto (4,2). Ou seja, o comprimento da reta é o mesmo, porém a reta se deslocou duas unidades para a direita e uma unidade para cima.

![image](http://1.bp.blogspot.com/-8NRD_tMkKMI/TeSFYcaEqaI/AAAAAAAAAJE/oyB127z7uqk/s320/figCRel02.png)

Este recurso é bastante interessante quando se deseja desenhar a mesma figura em várias posições diferentes. Veja um exemplo:
```latex
\draw[->,blue] (2,1) -- +(2,1);
\draw[->,blue] (3,3) -- +(2,1);
\draw[->,blue] (1,4) -- +(2,1);
```

![image](http://3.bp.blogspot.com/-nHwyt0tuQxc/TeSFllg0OpI/AAAAAAAAAJI/9akmFKz7vhI/s1600/figCRel03.png)

__Exemplo 6__: retângulo
Vamos desenhar o mesmo retângulo da figura anterior, só que agora nos preocuparemos com seu comprimento e sua altura.
```latex
\draw[blue] (1,1) rectangle +(3,2);
```

O ponto inicial é o mesmo P1 dado por (1,1) só que agora o comprimento é 3 unidades e a altura é 2 unidades.

![image](http://2.bp.blogspot.com/-xT8P1jypXic/TeSFrtYBE7I/AAAAAAAAAJM/n4SeTdXqA9k/s1600/figCRel04.png)

#####Diferença entre + e ++

Em coordenadas relativas podemos usar os símbolos + e ++. A diferença é que enquanto ++ __atualiza__ as coordenadas em relação ao __último__ ponto, o + não atualiza, permanecendo sempre em relação ao ponto inicial da figura.

Veja na figura a seguir que com o uso de ++ a coordenada é sempre relativa ao último ponto da figura.
```latex
\draw[->,blue] (2,1) -- ++(1,0) -- ++(0,-1) -- ++(-1,0) -- ++(0,1);
```

![image](http://3.bp.blogspot.com/-K7EFJYw6J9o/TeSFzsbaAFI/AAAAAAAAAJQ/VUtKLGrAnao/s640/figCRM01.png)

No primeiro quadro a figura começa tendo P1 como origem e P2 como ponto final da linha;
No segundo quadro a origem é P2 e o ponto final é P3;
No terceiro quadro a origem é P3 e o ponto final é P4;
E no quarto quadro a origem é P4 e o ponto final é P1.

Na figura seguinte o uso de + tem sempre o ponto (2,1) como ponto de referência.
```latex
\draw[->,blue] (2,1) -- +(1,0) -- +(0,-1) -- +(-1,0) -- +(0,1);
```

![image](http://3.bp.blogspot.com/-TM40LeYAcvQ/TeSF9fB75tI/AAAAAAAAAJU/BWDNviO03mk/s640/figCRM02.png)

O ponto P1 em (2,1) permanece fixo e os demais pontos têm sempre o ponto P1 como origem.


#####Coordenadas Polares

O sistema de [coordenadas polares] consiste de uma distância (ou raio) e da medida de um ângulo em relação a um ponto fixo O chamado de __pólo__ e uma semi-reta fixa chamada de __eixo polar__.

![image](http://4.bp.blogspot.com/-QwiLlWNfIHA/TeSGFkRO-kI/AAAAAAAAAJY/8domJxZQrNk/s320/figCPol01.png)

O ponto P fica bem determinado através do par ordenado (\alpha:r), onde \alpha é a medida (em graus) do ângulo orientado AOP, e r é a distância (ou raio) entre a origem e o ponto P. Note que o ângulo segue o sentido __anti-horário__ em relação ao ponto O.

Veja a seguir como é uma grade em coordenadas polares.

![image](http://3.bp.blogspot.com/-AD73wafLkJs/TeSGL49VM4I/AAAAAAAAAJc/C5ctrZNacl4/s400/figCPol02.png)

Vejamos alguns exemplos de retas desenhadas em coordenadas polares:

__Exemplos 7 e 8__
```latex
\draw (0,0) -- ++(45:2);

\draw (0,0) -- ++(135:3);
```

![image](http://4.bp.blogspot.com/-H1hg5mo6fzs/TeSGW4OkwyI/AAAAAAAAAJg/tvT5nEACzCM/s200/figCPol03.png)

![image](http://3.bp.blogspot.com/-s7kNADsi2pc/TeSGc9uHKoI/AAAAAAAAAJk/ZecUNEsJgsU/s200/figCPol04.png)

__Exemplos 9 e 10__
```latex
\draw (0,0) -- ++(210:2);

\draw (0,0) -- ++(315:3);
```

![image](http://4.bp.blogspot.com/-NbOK88ev2f4/TeSG8cc3ARI/AAAAAAAAAJo/IEu4btlV4iQ/s200/figCPol05.png)

![image](http://1.bp.blogspot.com/-5mQW_D-EqrU/TeSHA_YnshI/AAAAAAAAAJs/dz3fsRxQguI/s200/figCPol06.png)

Para o último exemplo podemos escrever \draw (0,0) -- ++(-45:3); ou seja, usando o sinal de - o ângulo muda para o sentido horário.

__Exemplos 11__: Combinando coordenadas relativas e coordenadas polares
Para que a origem da reta fique num ponto diferente de (0,0) precisamos combinar coordenadas relativas e coordenadas polares, para isso digite:
\draw (2,1) -- ++(45:2);

![image](http://3.bp.blogspot.com/-Gbfc8MDY31A/TeSHWRuou1I/AAAAAAAAAJw/uOZEDq77osQ/s320/figCPol07.png)

A reta inicia-se em (2,1) e possui um ângulo de 45º e 2 cm de comprimento.

__Exemplos 12 e 13__: Losango e Círculo com raio
Um exemplo ideal para a utilização desta técnica é quando se deseja desenhar um losango de 3 cm de comprimento e inclinação de 60º.
```latex
\draw[fill=yellow] (0,0) -- (3,0) -- ++(60:2) -- ++(-3,0) -- cycle;
```

Ou um círculo de raio unitário com indicação do raio.
```latex
\begin{tikzpicture}[>=latex]
 \draw (2,1) circle (1);
 \fill (2,1) circle (1pt);
 \draw[->] (2,1) -- ++(45:1);
\end{tikzpicture}
```

Note que o círculo está fora da origem.

![image](http://2.bp.blogspot.com/-ZsnG7I8Y4zE/TeSHomwLBqI/AAAAAAAAAJ0/oKxsh9liHKk/s200/figLosango.png)

![image](http://4.bp.blogspot.com/-2txJbSAG5F8/TeSHszLOhfI/AAAAAAAAAJ4/PLYEioeKUT4/s200/figCirculo.png)

#####Operações algébricas com coordenadas

O TikZ calcula valores diretamente na entrada das coordenadas graças à 'biblioteca' calc.

__Exemplo 14__: Soma e subtração de coordenadas
```latex
\fill[red] (2,1) circle (2pt);
\fill[blue] (2+1,1+1) circle (2pt);
\fill[blue] (2-1,1-1) circle (2pt);
```

O ponto P2 foi obtido pela soma de 1 unidade em cada uma das entradas da coordenada. E o ponto P3 pela subtração de 1 unidade em cada uma das entradas.

![image](http://3.bp.blogspot.com/-Ny70l6wfq1U/TeSICuZzAMI/AAAAAAAAAJ8/vbRFymqCW-8/s320/figCalc01.png)

__Exemplo 15__: Multiplicação e divisão de coordenadas
```latex
\fill[red] (2,1) circle (2pt);
\fill[blue] (2*2,1*2) circle (2pt);
\fill[blue] (2/2,1/2) circle (2pt);
```

O ponto P2 foi obtido pela multiplicação por 2 em cada uma das entradas da coordenada, resultando assim no ponto (4,2). E o ponto P3 pela divisão por 2 em cada uma das entradas, resultando no ponto (1,0.5).

![image](http://1.bp.blogspot.com/-OVVE7wii0A8/TeSIIW0XXlI/AAAAAAAAAKA/W6S2dDI26-Y/s320/figCalc02.png)

__Exemplo 16__: Medidas no losango
```latex
\begin{tikzpicture}[>=latex]
 \draw[fill=yellow] (0,0) -- (3,0) -- ++(60:2) -- ++(-3,0) -- cycle;
 \draw[->] (0,0) ++(.5,0) arc (0:60:.5);
 \node[below] at (3/2,0) {$3$};
 \node at (45/2:1) {$60^\circ$};
\end{tikzpicture}
```

Repare nas linhas a seguir o uso do operador de divisão.
```latex
\node[below] at (3/2,0) {$3$};
\node at (45/2:1) {$60^\circ$};
```

![image](http://2.bp.blogspot.com/-setHva_mFXE/TeSINcnzYBI/AAAAAAAAAKE/2a4MknQbLCg/s200/figCalc03.png)

#####Nomeando coordenadas

Um recurso muito interessante no TikZ é a possibilidade de usar pontos nomeados. Para nomear uma coordenada escreva:
```latex
\coordinate (A) at (0,0);
\coordinate (B) at (2,1);
```

Agora temos o ponto A na coordenada (0,0) e o ponto B na coordenada (2,1). Agora podemos desenhar uma reta do ponto A ao ponto B.
```latex
\draw (A) -- (B);
```

![image](http://1.bp.blogspot.com/-tiQkd5xQItw/TeSIYZjamXI/AAAAAAAAAKI/halaTc1Q0L8/s200/figCo01.png)

Veja o código completo:
```latex
\begin{tikzpicture}
 \coordinate[label=left:A] (A) at (0,0);
 \coordinate[label=right:B] (B) at (2,1);
 \draw (A) -- (B);
\end{tikzpicture} 
```

As opções label=left:A e label=right:B colocam uma legenda a esquerda de __A__ e a direita de __B__, respectivamente.
Também é possível desenhar um ponto e nomeá-lo logo na sequência. Digite:
```latex
\draw (A) -- (B) -- (4,0) coordinate[label=right:C] (C);
```

Acabamos de nomear o ponto __C__ na coordenada (4,0) diretamente no desenho da reta.
Agora podemos fechar o triângulo.
```latex
\draw (A) -- (C);
```

Veja o código completo:
```latex
\begin{tikzpicture}
 \coordinate[label=left:A] (A) at (0,0);
 \coordinate[label=above:B] (B) at (2,1);
 \draw (A) -- (B) -- (4,0) coordinate[label=right:C] (C);
 \draw (A) -- (C);
\end{tikzpicture}
```

![image](http://1.bp.blogspot.com/-jtGVE4dZZRk/TeSIhttHHmI/AAAAAAAAAKM/C0AAktm1464/s320/figCo02.png)

__Exemplo 17__: Reta paralela com comprimento definido
No código a seguir vamos desenhar uma reta paralela aos pontos __A__ e __B__ começando por __C__, que está a uma distância de 3mm de A, e com comprimento de 1cm.

```latex
\begin{tikzpicture}
 \coordinate[label=left:A] (A) at (1,1);
 \coordinate[label=right:B] (B) at (2,1);
 \fill[blue] (A) circle (1pt);
 \fill[blue] (B) circle (1pt);
 \draw[->,red] (A)++(0,3mm) coordinate[label=C] (C) -- ++(1,0);
 \fill[red] (C) circle (1pt);
\end{tikzpicture}
```


Observe na linha ```\draw[->,red] (A)++(0,3mm) coordinate[label=C] (C) -- ++(1,0);``` que o ponto (A)++(0,3mm) é chamado de __C__. Somente dessa forma que ele pode ser computado para a coordenada onde se encontra, e a partir dai ser usado como ponto __C__.

![image](http://1.bp.blogspot.com/-GYxe4ZCpUno/TeSIoPsQ2_I/AAAAAAAAAKQ/wsAqhHCTVNs/s320/figCo03.png)

__Exemplo 18__
É claro que podemos usar o mesmo ponto várias vezes.
```latex
\begin{tikzpicture}
 \coordinate (A) at (0,0);
 \coordinate (B) at (2,1);
%pontos
 \fill[blue] (A) circle (1pt) (B) circle (1pt);
%legendas
 \node[left] at (A) {A};
 \node[right] at (B) {B};
%retangulo
 \draw[fill=yellow] (A) rectangle (B);
%reta
 \draw (A) -- (B);
\end{tikzpicture}
```

![image](http://4.bp.blogspot.com/-YUiCGnCJaCU/TeSIs4xuBoI/AAAAAAAAAKU/qxUZtAgyC2k/s320/figCo04.png)

Este artigo também está disponível no [scribd].






[TikZ]:http://latexbr.blogspot.com/2011/01/desenhando-com-tikz.html

[retangulares]:http://pt.wikipedia.org/wiki/Sistema_de_coordenadas_cartesiano

[polares]:http://pt.wikipedia.org/wiki/Coordenadas_polares

[coordenadas retangulares]:http://www.im.ufrj.br/dmm/projeto/projetoc/precalculo/sala/conteudo/capitulos/cap21.html

[coordenadas cartesianas no plano]:http://pt.wikipedia.org/wiki/Sistema_de_coordenadas_cartesiano

[plano cartesiano]:http://pt.wikipedia.org/wiki/Sistema_de_coordenadas_cartesiano

[coordenadas polares]:http://pt.wikipedia.org/wiki/Coordenadas_polares

[scribd]:http://pt.scribd.com/doc/56692350/Sistemas-de-coordenadas-no-TikZ