Texto automático com lipsum
===========================

:date: 2014-12-03 23:59
:tags: dicas, pacotes, lipsum
:category: Dicas
:slug: texto-automatico-com-lipsum
:author: Regis da Silva
:email: regis.santos.100@gmail.com
:github: rg3915
:summary: O pacote lipsum serve para inserir um texto qualquer para exemplos...

Caso você queira inserir um texto qualquer apenas para exemplo mas não sabe o que escrever use o pacote `lipsum <http://ctan.tche.br/help/Catalogue/entries/lipsum.html>`_ .

Dentro do seu documento ``tex`` digite

.. code-block:: latex

    \documentclass[a4paper]{article}
    \usepackage{lipsum}
    \begin{document}
    	\lipsum[1-3]
    \end{document}

Note que o parâmetro ``[1-3]`` é opcional, se não colocar nada ele insere 7 parágrafos de texto, mas você pode escolher, além do exemplo, ``[23]`` que imprime o 23º parágrafo, em resumo as opções são:

.. code-block:: latex

    \lipsum
    \lipsum[23]
    \lipsum[1-150] % limite
