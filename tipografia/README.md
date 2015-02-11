	Este readme está totalmente desorganizado e incompleto...

# Tipografia (Fontes)

[Tipografia](http://pt.wikipedia.org/wiki/Tipografia) é a essência do [LaTeX](http://latexbr.blogspot.com/2010/04/introducao-ao-latex.html). Tipografia trata essencial de fontes e seus estilos, então veremos aqui um estudo completo sobre o uso de fontes no LaTeX. A escolha de uma fonte requer 4 características essenciais: família (family), série (serie), forma (shape) e tamanho (size). A seguir, veremos cada um deles.

*   [Codificação de caracteres](#subt1)
*   [Acentos, símbolos e caracteres especiais](#subt2)
*   [Enfatizando um texto](#subt3)
*   [Família (family)](#subt4)
*   [Séries (series)](#subt5)
*   [Formas (shape)](#subt6)
*   [Tamanho (size)](#subt7)
*   [Outras fontes](#subt8)
*   [Fontes matemáticas](#subt9)
*   [Fontes grandes](#subt10)
*   [Catálogo de fontes](#subt11)

Um exemplo simples:

``{\textit{\textsf{texto itálico sem serifa}}}``

%ver modo geral de selecionar fonte com
\selecfont

A fonte padrão do LaTeX é [Computer Modern](http://en.wikipedia.org/wiki/Computer_Modern), criado por [Donald Knuth](http://en.wikipedia.org/wiki/Donald_Knuth)

\familydefault = \rmdefault = Computer Modern Roman
\fontsize{10}{12} = \normalsize

* GUIA RÁPIDO (+ comandos)

### []()Codificação de caracteres

A codificação de caracteres vai além do ASCII. Para que o LaTeX reconheça os caracteres acentuados como 'á' ou 'ç' (cê-cedilha), por exemplo, é necessário uma codificação de entrada e uma de saída. A codificação é importante, pois dependendo do sistema operacional ou do editor usado os caracteres (acentuados) podem não ser interpretados corretamente.

O pacote que gerencia codificação de **entrada** é o

\usepackage{inputenc}

Para [Linux](http://latexbr.blogspot.com/2011/10/lancado-ubuntu-1110-oneiric-ocelot.html) a codificação padrão é a [unicode](http://pt.wikipedia.org/wiki/Unicode), então digite a opção

\usepackage[utf8]{inputenc}

Para _Windows_ o padrão é ISO, então digite

\usepackage[latin1]{inputenc}

Para _Mac_ experimente UTF8 ou applemac

\usepackage[applemac]{inputenc}

Caso haja a necessidade de converter seus arquivos ISO para UTF8, ou vice-versa, leia [Recodificando seus arquivos ISO para UTF8](http://latexbr.blogspot.com/2011/01/recodificando-seus-arquivos-iso-para.html).

O pacote que gerencia codificação de **saída** é o

\usepackage{fontenc}

por padrão use a opção

\usepackage[T1]{fontenc}

Para os exemplos a seguir vamos definir um preâmbulo básico:

\documentclass[a4paper]{article}
% cod. entrada
\usepackage[utf8]{inputenc} %Linux
%\usepackage[latin1]{inputenc} %Win
% cod. saida
\usepackage[T1]{fontenc}
% idioma
\usepackage[brazil]{babel}

\begin{document}
  ...
\end{document}

### []()Acentos, símbolos e caracteres especiais

Usando a codificação correta o LaTeX aceita entradas de acentos na forma tradicional (exemplo, "é ação"), porém o LaTeX possui uma entrada especial de caracteres acentuados. Sendo assim, a palavra _é ação_ pode ser digitada como <span class="Apple-style-span" style="font-family: 'Courier New', Courier, monospace;">\'e a\c c\~ao</span>. Este método pode ser usado sempre, indepedente da codificação usada. Veja a tabela a seguir:

#tabela: ja existe on line

Além disso, os caracteres especiais mais comuns são:

<table align="center" border="1" cellpadding="2" style="border-collapse: collapse;"><tbody>
<tr> <td>caracter</td> <td><div style="text-align: center;">
#</div>
</td> <td><div style="text-align: center;">
$</div>
</td> <td><div style="text-align: center;">
%</div>
</td> <td><div style="text-align: center;">
^</div>
</td> <td><div style="text-align: center;">
&amp;</div>
</td> <td><div style="text-align: center;">
_</div>
</td> <td><div style="text-align: center;">
{</div>
</td> <td><div style="text-align: center;">
}</div>
</td> <td><div style="text-align: center;">
~</div>
</td> </tr>
<tr>
<td>comando</td> <td><span class="Apple-style-span" style="font-family: 'Courier New', Courier, monospace;">\#</span></td> 
<td><span class="Apple-style-span" style="font-family: 'Courier New', Courier, monospace;">\$</span></td> 
<td><span class="Apple-style-span" style="font-family: 'Courier New', Courier, monospace;">\%</span></td> 
<td><span class="Apple-style-span" style="font-family: 'Courier New', Courier, monospace;">\^{}</span></td> 
<td><span class="Apple-style-span" style="font-family: 'Courier New', Courier, monospace;">\&amp;</span></td> 
<td><span class="Apple-style-span" style="font-family: 'Courier New', Courier, monospace;">\_</span></td> 
<td><span class="Apple-style-span" style="font-family: 'Courier New', Courier, monospace;">\{</span></td> 
<td><span class="Apple-style-span" style="font-family: 'Courier New', Courier, monospace;">\}</span></td> 
<td><span class="Apple-style-span" style="font-family: 'Courier New', Courier, monospace;">\~{}</span></td> 
</tr>
</tbody></table>

O LaTeX possui milhares de símbolos e eles estão documentados em [symbols](http://linorg.usp.br/CTAN/info/symbols/comprehensive/symbols-a4.pdf) de Scott Pakin ou digite
texdoc symbols

### []()Enfatizando um texto

O LaTeX enfatiza um texto de uma forma bem simples: se o texto estiver no modo normal ele enfatiza em _itálico_, caso contrário (texto em itálico) ele enfatiza para o modo normal.

O comando é \emph{}. Veja um exemplo.

Veja este texto \emph{enfatizado}.

\emph{Se o texto já estiver enfatizado a fonte \emph{normal} será usada para enfatizar este texto.}

% exemplo no site .png

### []()Família (family)

<div align="center">
<table align="center" border="1" cellpadding="2" style="border-collapse: collapse;"><tbody>
<tr> <td>**comando**</td> 
<td>**equivalente**</td> 
<td>**valor***</td> 
<td>**resultado**</td>
</tr>
<tr>
<td><span style="font-family: 'Courier New'; font-size: x-small;">\textrm{…}</span></td> 
<td><span style="font-family: 'Courier New';">{\rmfamily…}</span></td> 
<td><span style="font-family: 'Courier New';">cmr</span></td> <td>Romano (padrão)</td>
</tr>
<tr>
<td><span style="font-family: 'Courier New';">\textsf{…}</span></td> <td><span style="font-family: 'Courier New';">{\sffamily…}</span></td> <td><span style="font-family: 'Courier New';">cmss</span></td> <td>Sem serifa</td>
</tr>
<tr>
<td><span style="font-family: 'Courier New';">\texttt{…}</span></td> <td><span style="font-family: 'Courier New';">{\ttfamily…}</span></td> <td><span style="font-family: 'Courier New';">cmtt</span></td> <td>Monoespaço (<span style="font-family: 'Courier New';">máquina de escrever)</span></td></tr>
</tbody></table>
</div>
* Valor na classe _article_.

**Obs**: Os comandos da primeira coluna são mais recomendados que os da segunda coluna, pois o resultado nem sempre é o mesmo em relação ao espaçamento.

Muitas fontes do LaTeX requer algum pacote no preâmbulo, mas outras já são carregadas por padrão. Veja a seguir as famílias de fontes mais comuns.

Repare no uso de \selectfont, sem ele você pode obter resultados inesperados. Veja também as chaves {...} nos extremos, que seleciona o texto desejado, sem ele todo o texto após o comando terá a mesma aparência.

http://ctan.tche.br/help/Catalogue/entries/helvet.html
http://www.tug.dk/FontCatalogue/helvetica/

http://www.tug.org/fontname/html/Standard-PostScript-fonts.html

### []()Séries (series)

### []()Formas (shape)

### []()Tamanho (size)

### []()Outras fontes

### []()Fontes matemáticas

### []()Fontes grandes

### []()Catálogo de fontes

texdoc fontname

frase:
``A persistência é o caminho do êxito.'' (Charles Chaplin)

A vida só pode ser compreendida olhando-se para trás, mas só pode ser vivida olhando-se para frente. (Johnnie Walker)

- história de cada tópico (intro) em 'fntguide'

[Tipografia (especificações técnicas de uma caixa de texto)](http://pessoa.fct.unl.pt/p110371/nuno/category/typography/)

[Using common PostScript fonts with LaTeX](http://ceres.cisc.usp.br/CTAN/macros/latex/required/psnfss/psnfss2e.pdf) ou texdoc psnfss2e
-> tabela com as fontes mais comuns do LaTeX

[fontes disponíveis no TeXLive](http://ctan.tche.br/info/fontsampler/sampler.pdf)
[LaTeX Fonts](http://suppiya.files.wordpress.com/2008/02/latex_fonts.pdf) de Ki-Joo Kim
[symbols](http://linorg.usp.br/CTAN/info/symbols/comprehensive/symbols-a4.pdf) de Scott Pakin
[]()

% a nice font for the title
\usepackage[sf]{vivaldi}

microtype

Referências

texdoc classes

\fontencoding{T1}
\fontfamily{garamond}
\fontseries{m}
\fontshape{it}
\fontsize{12}{15}
\selectfont

Outras fontes

ver as fontes do psnfss2e pág. 8, lista-las e fazer exemplos.

http://ctan.tche.br/help/Catalogue/entries/helvet.html
http://www.tug.dk/FontCatalogue/helvetica/

http://www.tug.org/fontname/html/Standard-PostScript-fonts.html

[]()
[LaTeX2e font selection](http://linorg.usp.br/CTAN/macros/latex/doc/fntguide.pdf) ou texdoc fntguide
[Font selection in LATEX: The most frequently asked questions](http://www.tug.org/pracjourn/2006-1/schmidt/schmidt.pdf)
[Fonts and TeX](http://tug.org/fonts/)
(1) [Wikibooks fonts](http://en.wikibooks.org/wiki/LaTeX/Formatting#Fonts)
[Finding the font name (TeX.SX)](http://tex.stackexchange.com/questions/25249/how-do-i-use-a-particular-font-for-a-small-section-of-text-in-my-document/25251#25251)
[LaTeX - Codificação de entrada e de saída](http://www.tecepe.eng.br/blog/tex/latex/latex-codificacao-de-entrada-e-de-saida)
[]()

Palavras-chave: Tipografia, Fontes, trabalhando com fontes no LaTeX, editando fontes no LaTeX.