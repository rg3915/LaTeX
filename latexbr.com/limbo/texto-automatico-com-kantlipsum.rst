Texto automático com kantlipsum
===============================

:date: 2014-12-03 23:59
:tags: dicas, pacotes, kantlipsum
:category: Dicas
:slug: texto-automatico-com-kantlipsum
:author: Regis da Silva
:email: regis.santos.100@gmail.com
:github: rg3915
:summary: Se você estiver enjoado do lipsum use o kantlipsum, o texto é em inglês...

Se você estiver enjoado de usar o `lipsum <>`_ então use o `kantlipsum <>`_ , onde o texto é em inglês.

Dentro do seu documento ``tex`` digite

.. code-block:: latex

    \documentclass[a4paper]{article}
    \usepackage[numbers]{kantlipsum}
    \begin{document}
    	\kant
    \end{document}

Note que os parágrafos podem ser numerados por opção.

As formas de escolher os parágrafos é semelhante ao *lipsum*.

.. code-block:: latex

    \kant
    \kant[23]
    \kant[1-100]

