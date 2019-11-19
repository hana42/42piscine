### [back](https://github.com/hana42/42piscine/tree/master/Shell01)

------------------------------------------
#### Objetivo:


* Escreva uma linha de comando que mostre o número de arquivos regulares e de
pastas dentro da pasta atual e todas as suas subpastas, incluindo o "." da pasta
inicial.
* Exemplo de saída:
```
$>./count_files.sh | cat -e
42$
$>
```

```
$ man wc
```

-----------------------------------------
#### UTILIZE O GOOGLE!
Se nós procurarmos por [`Como contar a quantidade de arquivos dentro de um diretório no Linux`](https://devblog.drall.com.br/como-contar-a-quantidade-de-arquivos-dentro-de-um-diretorio-no-linux)

ou

[`Recursively counting files in a Linux directory`](https://stackoverflow.com/questions/9157138/recursively-counting-files-in-a-linux-directory)

Encontraremos uma variedade de respostas parecidas com essa:

`find DIR_NAME -type f | wc -l`

**Explicação:**
* Substituímos *DIR_NAME* por __.__ para executar o comando na pasta atual.
* Removemos o __-type f__ porque ele limita a pesquisa a APENAS arquivos.
* __|__ redireciona a saída padrão do comando find para a entrada padrão do comando wc.
* __wc__ (abreviação de word count) conta caracteres, palavras e/ou linhas dos dados da entrada padrão e apresenta o resultado na saída padrão.
* __-l__ para contar apenas linhas.

**Resultado:**
`find . | wc -l`

> Nota: Lembre-se de tornar o arquivo executável para não ter essa mensagem de erro: 'bash: ./count_files.sh: Permission denied' usando este comando:
```
$ chmod u+x count_files.sh
```

------------------------------------------
### [back](https://github.com/hana42/42piscine/tree/master/Shell01)
