### [back](https://github.com/hana42/42piscine/tree/master/Shell00)

------------------------------------------
#### Objetivo:
Crie o arquivo midLS com o comando a ser utilizado para listar os arquivos e diretórios da pasta atual.
```
$ midLS
```
__Notas__: o comando não deverá mostrar os arquivos ocultos, nem "." ou ".."

Os arquivos devem ser separados por vírgulas e ordenados por data de criação.

Os diretórios devem ser seguidos de uma barra.

* O que não é pedido, não é para ser feito!


------------------------------------------
###   RTFM!
Se utilizarmos o comando `man ls` para uma lista das opções do comando `ls` veremos que:
```
-m: fill width with a comma separated list of entries
-p: append / indicator to directories
-t: sort by modification time, newest first
-U: do not sort; list entries in directory order
```
> Aqui há um problema, porque com o comando ls não podemos realmente classificar os resultados por data de criação, somente por data de modificação. Isso é dado porque a maioria dos UNIXs não tem um conceito de tempo de criação do arquivo, portanto, essas informações não são registradas.


#### Criando o arquivo
Para criar o arquivo `midLS` nós podemos utilizar `vim midLS`
e digitar o comando `ls -mptU`  dentro dele.

> De acordo com "o que não é pedido, não é para ser feito!" o correto seria `-mpU`, o teste fica por sua conta e risco.


------------------------------------------
### [back](https://github.com/hana42/42piscine/tree/master/Shell00)
