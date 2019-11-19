### [back](https://github.com/hana42/42piscine/tree/master/Shell01)

------------------------------------------
#### Objetivo:

Criar um arquivo contendo somente "42" e nada mais.
```
>ls -lRa *MaRV* | cat -e
-rw---xr-- 1 75355 32015 2 Oct 2 12:21 "\?$*'MaRViN'*$?\"$
```

- Fun fact: O nome vem do personagem Marvin, o Androide Paranoide de O Guia do Mochileiro das Galáxias, que também foi inspiração para a música [Paranoid Android](https://www.youtube.com/watch?v=fHiGbolFFGw) do Radiohead.
-----------------------------------------

#### Existem duas soluções (que eu conheço) para isso:
* O mais fácil é usar o comando `touch` para criar o arquivo, e para formatar o nome como no exercício utilizamos o backslash `\` antes de cada caractere especial:
```
touch \"\\\?\$\*\’MaRViN\’\*\$\?\\\"
```
* E a outra maneira é apenas criar um arquivo temporário com o nome que você deseja e renomeá-lo para `"\?$*’MaRViN’*$?\"` com o comando `mv`
> Utilize seu editor de texto preferido para incluir o '42' dentro desse arquivo depois de concluir as etapas anteriores. Dica: `tab` completa o nome do arquivo automaticamente para você. :wink:

------------------------------------------

__Edit:__ Olhando minhas anotações, há um detalhe que não me recordo se é necessário. Se repararmos, o arquivo mostrado no exemplo possui exatos 2 bytes.

#### Para chegarmos a isso:
- Abra o arquivo no vim `vim "\?$*'MaRViN'*$?\"`
- Aperte esc e digite `:set binary` e dê enter
- Novamente, esc e digite `:set noeol` → No End Of Line, remove o `\n` adicionado automaticamente no fim da string.

------------------------------------------
### [back](https://github.com/hana42/42piscine/tree/master/Shell01)
