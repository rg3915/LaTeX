Usando LaTeX por linha de comando
=================================

:date: 2014-12-03 23:59
:tags: dicas, DOS, linha de comando, terminal
:category: Dicas, DOS, linha de comando, Terminal
:slug: usando-latex-por-linha-de-comando
:author: Regis da Silva
:email: regis.santos.100@gmail.com
:github: rg3915

Compilar através de linha de comando se torna bastante útil quando precisamos usar comandos adicionais e/ou recursos sofisticados. Quem gosta de usar o **terminal** sabe do que estou falando.

No Windows você usa o **DOS**, no Linux você usa o **terminal**.

Suponha que você tenha um arquivo chamado `exemplo.tex <http://>`_ .

Vá até a pasta do seu projeto

.. code-block:: bash

    $ cd pasta/

Veja o video no `youtube <http://>`_ .

Compilando DVI, PS e PDF
------------------------

Como vimos na `introdução <http://>`_ podemos gerar documentos em **DVI, PS** e/ou **PDF**.

Para gerar **DVI** digite

.. code-block:: bash

    $ latex exemplo

Repare que não precisa da extensão ``.tex``, mas para gerar **PS** precisa

.. code-block:: bash

    $ dvips exemplo.dvi

Obviamente precisamos do primeiro comando para obter o DVI e gerar o PS a partir dele.

E finalmente para converter de PS para **PDF**

.. code-block:: bash

    $ ps2pdf exemplo.ps

Esta sequência de comandos se torna necessária quando se tem figuras **EPS** embutida no seu trabalho.

Compilando direto para PDF
--------------------------

Para compilar direto para **PDF** digite

.. code-block:: bash

    $ pdflatex exemplo

**Obs**: Este comando não serve quando tiver figuras EPS embutida.

Se desejar, também pode usar um comando para converter de DVI direto para PDF.

.. code-block:: bash

    $ dvipdfm exemplo

Visualizando o documento
------------------------

Para visualizar o documento direto pelo terminal digite

.. code-block:: bash

    $ evince exemplo.pdf # linux ou
    $ exemplo.pdf # win

Veja a seguir um esquema dos processos de compilação.

.. image:: path

Veja o video no `youtube <http://>`_ .