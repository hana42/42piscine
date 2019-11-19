### [back](https://github.com/hana42/42piscine/tree/master/Shell01)

------------------------------------------
#### Objetivo:

* Escreva uma linha de comando que determine e mostre a lista de grupos dos quais
o login especificado na variável de ambiente FT_USER é membro, separando-os
por vírgulas sem espaços.
- Exemplos:
	1. para FT_USER=nours, o resultado é :
  ```
  $ ./print_groups.sh
  god,root,admin,master,nours,bocal
	```
	2. para FT_USER=daemon, o resultado é :
	```
	$>./print_groups.sh
	daemon,bin$>
	```

> Busque o seguinte: `man groups` `man tr` `pipe` e `variáveis de ambiente` antes de continuar.

------------------------------------------
#### Se nós lermos o manual `man groups` veremos que:
```
NAME:
	groups - print the groups a user is in
SYNOPSIS:
	groups [OPTION]... [USERNAME]...
```
que nos permite criar o começo do comando:
```
$ groups $FT_USER
```

> O resultado do comando `$ groups $FT_USER` só mostrará a lista,
mas nós precisamos que ela esteja separada por vírgulas.

#### Para fazer a separação por vírgulas, utilizaremos o `man tr`:
```
NAME:
	tr - translate or delete characters
SYNOPSIS:
	tr [OPTION]... SET1 [SET2]
DESCRIPTION:
	Translate, squeeze, and/or delete characters from standard input, writing to
	standard output.
	-d, --delete
		delete characters in SET1, do not translate
```

> Nesse caso, precisaremos apenas de uma [OPÇÃO], porque o output de `groups $FT_USER` já traduz todos os grupos que o FT_USER pertence separado por um espaço e terminado com uma quebra de linha, então, só precisamos substituir os espaços por vírgulas, e excluir a quebra de linha (`\n`). Utilizando o tr:
```
$ tr ' ' ','
$ tr -d '\n'
```

Mas para esse comando funcionar, nós precisaremos de uma ferramenta chamada [`PIPE`](https://en.wikipedia.org/wiki/Pipeline_%28Unix%29).

Essa ferramenta é uma forma de redirecionamento de envio dados de um programa para outro.
É chamada de encadeamento (ou em inglês: pipeline) e o operador que usamos é (`|`) (encontra-se acima da
barra invertida (`\`) na maioria dos teclados).
##### O que esse operador faz?
Ele alimenta a saída do comando da esquerda como entrada para o comando à direita, então você pode combinar dois ou mais comandos. A saída do primeiro comando atua como entrada para outro comando, e a saída desse comando pode atuar como entrada para o próximo comando e assim por diante, sempre lendo os dados da esquerda para a direita.
No exemplo abaixo, listaremos apenas os 3 primeiros arquivos no diretório:
```
$ ls
exemplo1, exemplo2, exemplo3, exemplo4, exemplo5
$ ls | head -3
exemplo1
exemplo2
exemplo3
$
```

#### Resultado final:
Agora, podemos usar esses três elementos para criar a solução da seguinte forma:
```
#!/bin/sh
$ groups $FT_USER | tr ' ' ',' | tr -d '\n'
```

> Estude os comandos, faça testes e entenda o funcionamento de cada um antes de enviar o exercício.
------------------------------------------

### [back](https://github.com/hana42/42piscine/tree/master/Shell01)
