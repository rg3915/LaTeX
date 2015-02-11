Introdução ao LaTeX
===================

:date: 2014-12-03 23:59
:tags: introdução, latex
:category: Introdução
:slug: introducao-ao-latex
:author: Regis da Silva
:email: regis.santos.100@gmail.com
:github: rg3915
:summary: Veja aqui o making off de como foi feito este site...

A essência do `LaTeX <http://pt.wikipedia.org/wiki/LaTeX>`_ é a `tipografia <http://pt.wikipedia.org/wiki/Tipografia>`_ . Escrever em LaTeX é escrever com estilo, com elegância. Quem escreve em LaTeX está preocupado com qualidade de apresentação, qualidade de impressão. Quem escreve em LaTeX tem um gosto refinado pela arte da tipografia, pela arte de escrever bem, de maneira fácil e bem apresentável.

	Github: Todos os exemplos deste site estão no `github <http://>`_ .

`O que é LaTeX?`_ 
`O que podemos fazer com o LaTeX?`_
`Vantagens e desvantagens`_
`Como se cria um documento no LaTeX?`_
`O que eu preciso instalar para usar o LaTeX?`_
`Como instalar o LaTeX?`_
`Editando um documento no LaTeX`_
`Compilando no LaTeX`_
`Visualização e informações adicionais`_
`Onde obter ajuda?`_
`Sites`_

O que é LaTeX?
--------------

Em 1977 `Donald Knuth <http://pt.wikipedia.org/wiki/Donald_Knuth>`_ , autor do livro `The Art of Computer Programming <http://pt.wikipedia.org/wiki/The_Art_of_Computer_Programming>`_ , criou o `TeX <http://pt.wikipedia.org/wiki/TeX>`_ , (pronuncia-se *tec*), um sistema de `tipografia <http://pt.wikipedia.org/wiki/Tipografia>`_ cuja finalidade é escrever texto científico e fórmulas matemáticas sem se preocupar com a diagramação.

Na década de 80, `Leslie Lamport <http://pt.wikipedia.org/wiki/Leslie_Lamport>`_ criou o `LaTeX <http://pt.wikipedia.org/wiki/LaTeX>`_ , (pronuncia-se *lai-tec*), um conjunto de macros para o `TeX <http://pt.wikipedia.org/wiki/TeX>`_ . O `LaTeX <http://pt.wikipedia.org/wiki/LaTeX>`_ é um sistema de `diagramação <http://pt.wikipedia.org/wiki/Diagrama%C3%A7%C3%A3o>`_  de texto baseado em `tags <http://pt.wikipedia.org/wiki/Tag_(linguagens_de_marca%C3%A7%C3%A3o)>`_ (semelhante ao *html*, mas não igual), um conjunto de `comandos de alto nível <http://pt.wikipedia.org/wiki/Linguagem_de_programa%C3%A7%C3%A3o_de_alto_n%C3%ADvel>`_ que facilita a escrita de documentos preocupando-se apenas com o conteúdo.

O LaTeX está atualmente na versão LaTeX2e, existe um projeto para o LaTeX3, mas não concluido ainda.

O LaTeX é um sistema multiplataforma, funciona tanto `online <http://>`_ como em sistemas desktop como Windows, Linux e OSX.

O que podemos fazer com o LaTeX?
--------------------------------

O LaTeX é amplamente utilizado no meio acadêmico para a produção de textos científicos devido sua alta qualidade tipográfica. Com o LaTeX é possível escrever artigos científicos, monografias, teses, dissertações, livros, apresentações de slides, listas de exercícios, cartas formais, *curriculum vitae*, posters, etc.

Além disso, no LaTeX é possível trabalhar com fórmulas matemáticas, imagens vetoriais, listas, tabelas, índices remissivos, ambientes personalizados, etc. tudo com uma alta qualidade de impressão e diagramação.

Vantagens e desvantagens
------------------------

**Vantagens**

* Produção de texto com qualidade tipográfica
* Preocupação apenas com o conteúdo
* Multiplataforma e *open source*
* Cria diversos tipos de documentos desde artigos e livros até apresentação de slides
* É possível reutilizar as mesmas configurações pré-definidas para diversos documentos diferentes
  
**Desvantagens**

* Não é `WYSIWYG <http://pt.wikipedia.org/wiki/WYSIWYG>`_ , ou seja, você não vê o resultado direto na tela como num MS Word ou Libre Office. Você escreve o texto junto com algumas *tags* e depois de `compilado <http://>`_ que você vê o resultado, normalmente em PDF.
* O aprendizado não é tão intuitivo, mas a documentação é ampla, começando por este site, que espero que seja sua referência.

Mas não desanime, depois que você aprender LaTeX de verdade você vai dizer "*Word nunca mais!*"

Como se cria um documento no LaTeX?
-----------------------------------

Para produzir um documento em LaTeX precisamos de 3 procedimentos básicos:

figura - edição, compilação e visualização

Edição
^^^^^^

Primeiro editamos um arquivo com a extensão ``.tex`` usando a linguagem de *tags* do LaTeX. Este arquivo contém essencialmente um **preâmbulo** e o **corpo do texto**. É no corpo do texto que inserimos as figuras e fórmulas matemáticas.

Compilação
^^^^^^^^^^

É o processo que transforma o arquivo ``.tex`` no formato final, geralmente PDF.

Visualização
^^^^^^^^^^^^

O resultado final é um documento PDF, que podemos visualizar e imprimir.

O que eu preciso instalar para usar o LaTeX?
--------------------------------------------

Nada. Você pode usá-lo online. Para isso leia `Editores on line <http://>`_ .

Como instalar o LaTeX?
----------------------

Mas e se eu quiser instalar o LaTeX para usar off line no meu computador?

Então você vai precisar de

* um `editor de texto <http://>`_
* uma **distribuição** dos pacotes do LaTeX
* um **visualizador** de PDF - Adobe Reader ou Evince (Linux).

Editor de texto
^^^^^^^^^^^^^^^

Para simplificar você pode usar ou **Notepad++** (Win) ou **Gedit** (Linux), mas um editor bem legal é o `Sublime Text 3 <http://>`_ .

Além disso, recomendo que você veja outros editores de texto em `Editores LaTeX IDE <http://>`_ .

Distribuição dos pacotes do LaTeX
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

O LaTeX é composto por vários pacotes menores que executam tarefas específicas, desde a edição, diagramação até a compilação do documento.

Existem dois:

`MiKTeX <http://>`_ 

**Vantagens**

* Fácil para instalar
* Você pode fazer uma instalação mínima e adicionar novos pacotes conforme a necessidade
* Versão *portable*
* Preview rápido com **Yap**
* *Open source*

**Desvantagens**

* Somente para Windows
* 
* 

O MiKTeX é bem fácil de instalar, entre no site e tente.

`TeX Live <http://>`_ 

**Vantagens**

* Multi plataforma
* 
* *Open source*

**Desvantagens**

* 
* 
* 

Veja em `Instalando TeXLive <http://>`_ como instalar o TeXLive. Recomendo que você instale também o `TeXmaker <http://>`_ .

Por fim veja este video onde mostro a instalação do `LaTeX no Windows <http://>`_ com TeXLive + Sublime Text 3 + Adobe Reader e a instalação do `LaTeX no Ubuntu <http://>`_ TeXLive + Sublime Text 3 + Evince.

Editando um documento no LaTeX
------------------------------

Abra um editor de texto de sua preferência e salve um arquivo com o nome `exemplo.tex <http://>`_ .

Veja a seguir um exemplo mínimo do mínimo para se criar um documento em LaTeX.

.. code-block:: latex

    \documentclass{article}
    % preâmbulo
    \begin{document}
    	% corpo do texto
    	Escreva seu texto aqui
    \end{document}

Isso aqui é o mínimo e suficiente para se criar um documento em LaTeX, onde o **preâmbulo** são todos os comandos de configuração, que ficam antes de ``\begin{document}``. O que estiver entre ``\begin{document}`` e ``\end{document}`` será o seu texto impresso. Comentários são marcados com o símbolo ``%``, isto não será impresso.

Mas o ``exemplo.tex`` minimalista que eu recomendo é

.. code-block:: latex

	% exemplo.tex
	\documentclass[a4paper]{article} % padrao 10pt
	\usepackage[utf8]{inputenc} % codificacao de caracteres
	\usepackage[T1]{fontenc} % codificacao de caracteres
	\usepackage[brazil]{babel} % tudo em portugues
	\usepackage{amsmath, amsfonts, amssymb} % para simbolos matematicos

	\title{Exemplo \LaTeX}
	\author{Seu Nome}
	\date{\today}    % para ocultar a data digite: \date{ }
	%--------------------------------------------------------------
	\begin{document}
	\maketitle  % cria o titulo na capa

	Escreva seu texto aqui...

	\end{document}

Tudo que se encontra entre ``{}`` são comandos obrigatórios, e entre ``[]`` são comandos opcionais.

Por padrão o tamanho do papel é ``letterpaper``, por isso colocamos ``a4paper``.

``inputenc`` é um pacote que escreve "de forma correta" a acentuação, no caso, usamos ``utf8``.

``babel`` é um pacote que traduz itens do documento como, *abstract*, *summary*, *index, chapter, section* para o idioma de sua preferência.

``amsmath, amsfonts, amssymb`` são pacotes que inserem símbolos e fontes matemáticas, como XXXXXXXXXXXXXX e R (real) xxxxxxxxxxxx, mas eu vou explicar melhor sobre estes pacotes em `link_variable_name <http://>`_ .

*Título*, *autor* e *data*... além do que está no exemplo a data pode ser ``\date{2014}`` também, por exemplo.

Tudo isso foi o nosso preâmbulo.

Para imprimir o título, autor e data usamos o comando ``\maketitle``.

Compilando no LaTeX
-------------------

Cada IDE tem o seu ícone para compilar, e é facilmente identificável. Então, de uma forma generalista vamos compilar usando o **DOS** (Win) ou **terminal** (Linux). Entre na pasta do seu projeto.

.. code-block:: bash

	$ cd sua_pasta/
    $ pdflatex exemplo.tex

Depois de compilado são criados alguns arquivos auxiliares. O mais importante deles é o arquivo ``exemplo.log`` que mostra erros encontrados durante a compilação, normalmente algum erro de digitação ou falta de pacote no preâmbulo, qualquer erro na verdade. Os demais (``.aux, .out, .nav, .snm, .toc, .vrb``) só são úteis durante a compilação, depois podem ser excluidos sem dó.

**Importante:** não se esqueça que o arquivo mais importante é o ``exemplo.tex``, sugiro até que você faça **backup** dele pra não chorar depois.

Leia mais em `Usando LaTeX por linha de comando <http://>`_ .


Visualização e informações adicionais
-------------------------------------

Na verdade nem precisava deste tópico porque visualização subentende-se pelo arquivo final em PDF. Mas...

No princípio era o **TeX** que gerava um documento final em `DVI <http://en.wikipedia.org/wiki/Device_independent_file_format>`_ , e isto era bom. Havia também o `PS <http://pt.wikipedia.org/wiki/PostScript>`_ e isto também era bom. Mas o que mais nos interessa hoje é o **PDF**.

Veja como converter para todos estes formatos em `Usando LaTeX por linha de comando <http://>`_ .


Onde obter ajuda?
-----------------

Se eu não conseguir te ajudar através deste site você pode obter ajuda de várias formas:

`IshortBR <http://repositorios.cpai.unb.br/ctan/info/lshort/portuguese-BR/lshortBR.pdf>`_ - "Uma não tão curta introdução ao LaTeX" este é o manual mais famoso e indicado para se aprender LaTeX, tanto que eu escrevi o `Tutorial LaTeX em 5 min <http://latexbr.blogspot.com.br/2012/07/aprendendo-latex-em-5-minutos.html>`_ baseado nele.

Veja também um **exemplo** do próprio **Leslie Lamport** em `sample2e.tex <http://>`_ .

`Sadao Massago <http://www.dm.ufscar.br/profs/sadao/latex/tex-examples.php?lang=pt>`_  - aprenda LaTeX via exemplos do prof. Sadao Massago, da `UFSCar <http://www.dm.ufscar.br/profs/sadao/>`_ .

`first-latex-doc.pdf <http://linorg.usp.br/CTAN/info/first-latex-doc/first-latex-doc.pdf>`_ (inglês) - guia rápido de LaTeX.

`Andrew Roberts <http://www.andy-roberts.net/writing/latex>`_ (inglês) site com exemplos.

`Online tutorials on LaTeX <http://www.tug.org/tutorials/tugindia/>`_ (inglês) tutorial online da TUGIndia.

`Mathmode <http://linorg.usp.br/CTAN/info/math/voss/mathmode/Mathmode.pdf>`_ (inglês) manual oficial sobre como escrever fórmulas matemáticas no LaTeX.

`Principais comandos LaTeX <http://latexbr.blogspot.com.br/2012/07/cartao-com-principais-comandos-do-latex.html>`_ traduzi o cartão de comandos original do `Winston Chang <http://www.stdout.org/~winston/latex/latexsheet-a4.pdf>`_ .

`The Comprehensive LaTeX Symbol List <http://ftp.snt.utwente.nl/pub/software/tex/info/symbols/comprehensive/symbols-a4.pdf>`_ - lista de símbolos e caracteres especiais do LaTeX, leitura recomendada.

Bom, eu coloquei estes links porque eu também leio eles até hoje, mas se você não quiser ler em inglês então leia o meu site.

TeXdoc
^^^^^^

Depois que você instala o **TeXLive** ele vem com a documentação completa de todos seus pacotes, veja alguns exemplos. Abra o **terminal** e digite

.. code-block:: bash

    $ texdoc latex

que você terá um guia da documentação online, ou então digite

.. code-block:: bash

    $ texdoc veryshortguide

que você terá um resumo de introdução ao LaTeX. Experimente também

.. code-block:: bash

    $ texdoc pgf

manual do PGF/TikZ.


Sites
-----

`LaTeX wikipedia <http://pt.wikipedia.org/wiki/LaTeX>`_ 

`LaTeX wikilivros <http://pt.wikibooks.org/wiki/Latex/Introdu%C3%A7%C3%A3o>`_ 

`tug.CTAN <http://tug.ctan.org/>`_ - atualmente é um dos sites com o repositório completo do conteúdo LaTeX.

`the TeX catalogue online <http://ctan.tche.br/help/Catalogue/brief.html>`_ - um catálogo completo de todos os pacotes LaTeX.

`TeXdoc <http://texdoc.net/>`_ documentação online

`tug.org <http://tug.org/>`_ site com notícias, novidades e informações sobre o mundo LaTeX. Ele também mostra os novos pacotes adicionados na distribuição.

`Font Catalogue <http://www.tug.dk/FontCatalogue/>`_ - catálogo de fontes, a essência da tipografia.

