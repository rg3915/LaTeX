Compilando com Rubber
=====================

:date: 2014-12-03 23:59
:tags: compilador, linha de comando, linux
:category: Compilador, linha de comando, Linux
:slug: compilando-com-rubber
:author: Regis da Silva
:email: regis.santos.100@gmail.com
:github: rg3915

O `Rubber <http://>`_ é um `build system <http://>`_ para LaTeX. Sua finalidade é compilar quantas vezes for necessário para resolver problemas ao gerar o documento final, como por exemplo, referências BibTeX, makeindex, etc.

A vantagem é que com o `Rubber <http://>`_ podemos compilar os documentos LaTeX completamente com uma única linha de comando.

	**PS**: o *Rubber* é usado no **Linux** via **terminal**.

Instalando
----------

.. code-block:: bash

    $ sudo apt-get install rubber

Usando o Rubber
---------------

Suponha que você tenha um arquivo chamado `exemplo.tex <http://>`_ .

Compilando e gerando o **DVI** (equivalente ao ``latex exemplo``)

.. code-block:: bash

    $ rubber exemplo

Compilando e gerando o **PDF** direto (equivalente ao ``pdflatex exemplo``)

.. code-block:: bash

    $ rubber -d exemplo

Gerando o **PS**

.. code-block:: bash

    $ rubber -p exemplo

Experimente também

.. code-block:: bash

    $ rubber -p -d exemplo

Este comando gera o **DVI**, converte para **PS** e depois para **PDF**.

Apagando os auxiliares que geraram o exemplo

.. code-block:: bash

    $ rubber --clean exemplo

Experimente também

.. code-block:: bash

    $ rubber -d exemplo1 exemplo2

Desta forma o Rubber compila os dois arquivos mencionados de uma vez.

Experimente também

.. code-block:: bash

    $ rubber -d *.tex

Assim, o Rubber compila todos os arquivos ``.tex`` da pasta.

Referências: `Rubber manual <http://manpages.ubuntu.com/manpages/oneiric/man1/rubber.1.html>`_ 