tutorial-latex-em-5min

Tutorial LaTeX em 5 minutos
===========================

# O Básico

## Estrutura do documento

Um documento `tex` pode ser agrupado ...


### Preâmbulo

O preâmbulo é a parte ...

**Exemplo 1** Relatório com fonte 10pt em papel A4

```latex
\documentclass[a4paper,10pt]{report}
```

Além disso, alguns pacotes são fundamentais.

```latex
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage[brazil]{babel}
```

### Ambientes

Todo ambiente começa com `\begin{}` e termina com `\end{}`. ...

```latex
\begin{document}
    ... texto do documento aqui
\end{document}
```