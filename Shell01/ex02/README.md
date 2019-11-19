### [back](https://github.com/hana42/42piscine/tree/master/Shell01)

------------------------------------------
#### Objetivo:


Escreva uma linha de comando que procure na pasta atual e em todas as subpastas todos os arquivos cujos nomes terminam com ".sh" (sem as aspas) e que só exiba os seus nomes, sem o .sh.
* Exemplo de saída:
```
$>./find_sh.sh | cat -e
find_sh$
file1$
file2$
file3$
$>
```
> Nota: Lembre-se de que a internet e o `MAN` são seus aliados...
------------------------------------------

Já vimos no [ex08](https://github.com/hana42/42piscine/tree/master/Shell00/ex08) do Shell00 como buscar arquivos dentro do diretório e aprendemos como criar um shell script:
```
#!/bin/sh
find . -type f -name "*.sh"
````

Agora, precisamos remover o ".sh" do output do comando:

#### Experimente googlar isso:

`using sed to remove file extension from find results`

No resultado da busca, encontramos essas formas de resolver:
* `-exec basename {} .sh \;`
* `sed 's/\.sh//'`
* `xargs -0 basename -a -s .sh`
> Lembrando que para utilizar mais de um comando, precisamos utilizar o `PIPE`
>> Ao invés de explicar aqui, recomendo estudar os comandos, eles serão úteis nos próximos exercícios:
##### Sed
1. [Sed - Introdução](https://www.vivaolinux.com.br/artigo/Sed-Introducao?pagina=3)
2. [30 Exemplos do comando Sed](https://terminalroot.com.br/2015/07/30-exemplos-do-comando-sed-com-regex.html)
##### Basename
1. [O comando basename](http://guialinux.uniriotec.br/basename/)
2. [wikipedia/Basename](https://en.wikipedia.org/wiki/Basename)
##### Xargs
1. [O comando xargs](http://www.dicas-l.com.br/cantinhodoshell/cantinhodoshell_20070226.php#.XdOqLehKiUk)
2. [Xargs - Construir e executar linhas de comando](http://www.bosontreinamentos.com.br/linux/certificacao-lpic-1/comando-xargs-construir-e-executar-linhas-de-comando-no-linux/)
3. [Utilização do -print0 com find e xargs](https://www.vivaolinux.com.br/dica/Dupla-diabolica-find-e-xargs)


---------------------------------------
#### Solução para a mensagem "./find_sh.sh Permission denied”:
```
$ chmod u+x find_sh.sh
```
------------------------------------------
### [back](https://github.com/hana42/42piscine/tree/master/Shell01)
