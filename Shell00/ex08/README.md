### [back](https://github.com/hana42/42piscine/tree/master/Shell00)

------------------------------------------
#### Objetivo:
Em um arquivo chamado clean, coloque a linha de comando que procurará todos os arquivos no diretório atual e seus subdiretórios que:
* Termine em ~ e todos os arquivos iniciados ou finalizados por #
* A linha de comando mostrará e apagará todos os arquivos encontrados.
* Apenas um comando é permitido: nenhum ';' ou '&&' ou outros comandos.
```
$ man find
```
-----------------------------------------

### O que ele faz?
O `find` é um comando para procurar arquivos, links, diretórios, etc no sistema.

Ele é utilizado da seguinte maneira:
```
$ find <diretório> <opções>
```
Sendo que:
1. O argumento <diretório> é o ponto de origem onde você quer começar a busca. Caso você queira procurar por todo o sistema para encontrar o arquivo, você pode utilizar `/` que é o sinal do diretório raiz, ou `.` para procurar no diretório atual.
2. O segundo argumento é o filtro que você quer utilizar para procurar seu arquivo. Ele pode ser nome do arquivo, tipo, data de criação ou modificação etc.


* Utilizamos o `man find` para chegar nessa solução:

```
find . -type f \( -name "*~" -o -name "#*#" \) -print -delete
```

```
-type [c]
	File is of type c:
	f (regular file)
-name [pattern]
	Base of file name (the path with the leading directories removed)
	matches shell pattern.
-print [format]
-delete:
	Delete  files;  true  if  removal succeeded.  If the removal failed,
	an error message is issued.  If -delete fails, find's exit status will
	be nonzero (when it eventually exits).  Use of -delete automatically
	turns on the `-depth' option.
-o:
	Ensures that the right hand side is evaluated only for those directories
	which didn't get deleted before.
```

------------------------------------------
### [back](https://github.com/hana42/42piscine/tree/master/Shell00)
