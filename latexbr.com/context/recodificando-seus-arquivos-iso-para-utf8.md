Recodificando seus arquivos ISO para UTF8
=========================================

Recodificando seus arquivos ISO para UTF8
-----------------------------------------


As distribuições mais recentes do linux estão adotando a codificação de caracteres utf-8. Para converter seus arquivos para o novo padrão veja no site [tex-br].

Como o site [tex-br] sai do ar. Vou escrever aqui os códigos para conversão dos arquivos:

De ISO para UTF:
recode -d l1..u8 arquivo.tex

De UTF para ISO:
recode -d u8..l1 arquivo.tex

Caso queira converter o arquivo para a acentuação do latex:
recode -d l1..tex arquivo.tex

Lembrete: o recode grava em cima do próprio arquivo. Para sua segurança, faça um back-up do arquivo antes de executar o comando, ou:
recode -d l1..tex < arquivo.tex

isso faz com que o resultado do recode seja mostrado direto na tela.





[tex-br]:http://www.tex-br.org/index.php/Recodificando_seus_arquivos