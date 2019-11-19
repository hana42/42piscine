### [back](https://github.com/hana42/42piscine/tree/master/Shell01)

------------------------------------------
#### Objetivo:

Escreva uma linha de comando que exiba um ls -l uma linha a cada duas (linha
sim, linha não), a partir da primeira.

-----------------------------------------

#### Podemos usar ls em combinação com awk:
* Primeiro, usamos o comando `ls -l` para exibir todo o conteúdo do diretório atual em formato de lista, depois passar os resultados utilizando o pipe `|` para o `awk` com a seguinte opção:
- `NR` número total de registros de entrada até agora.
- `% 2 ==` O `%` é um operador de módulo e `NR` é o número da linha atual, portanto, `NR % 2 == 0` é válido apenas para as linhas pares, e `NR % 2 == 1` para linhas ímpares.


- **Para linhas pares:**
```
ls -l | awk 'NR % 2 == 0'
```

- **Para linhas ímpares:**
```
ls -l | awk 'NR % 2 == 1'
```

__OU__

#### Podemos utilizar ls em combinação com o sed:

* Novamente, usamos o comando `ls -l` para exibir o conteúdo do diretório atual, depois passamos os resultados utilizando o pipe `|` para o `sed` com as seguintes opções:
- `-n`
   desativa o print automático e o sed só printa algo quando solicitado explicitamente pelo comando `p`.
- `"p;n"` ou `"n;p"`
   1. `p` printa a linha atual, sem passar para a linha seguinte.
   2. `n` move para a próxima linha sem printar nada na tela.

Depois que esses dois comandos são executados na linha atual, sed passa para a próxima linha e, em seguida, executa o comando novamente nesta nova linha. Esse script continuará sendo executado até que não haja mais linhas de entrada.

- **Para linhas  ímpares:**
```
ls -l | sed -n "p;n"
```

- **Para linhas pares:**
```
ls -l | sed -n "n;p"
```

------------------------------------------
### [back](https://github.com/hana42/42piscine/tree/master/Shell01)
