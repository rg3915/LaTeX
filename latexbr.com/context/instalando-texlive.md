instalando-texlive

Instalando TeXLive
==================

## Instalando o TeXLive no Windows


Entre em [Installing TeX Live over the internet](https://www.tug.org/texlive/acquire-netinstall.html) e baixe [install-tl-windows.exe][].

## Removendo TeX Live antigos (Linux)

Para instalar o TeX Live no Linux é necessário que você remova as versões antigas, caso tenha uma instalada.

Para isso abra o terminal e digite:

```
$ sudo rm -rf /usr/local/texlive
$ sudo rm -rf ~/.texlive2013
```

Remova o texto `PATH=/usr/local/texlive/2013/bin/i386-linux:$PATH de
gedit ~/.bashrc`

![alt text](http://2.bp.blogspot.com/-sj2fPuebqtU/U9MVwnVs5tI/AAAAAAAAA84/DBUnYtPCOto/s1600/TL1401.png)


