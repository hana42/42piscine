### [back](https://github.com/hana42/42piscine/tree/master/Shell01)

------------------------------------------
#### Objetivo:


* Escreva uma linha de comando que mostre os endereços MAC de sua máquina.
Cada endereço deve ser seguido de uma quebra de linha.

```
$ man ifconfig
```
-----------------------------------------

#### Primeiro vamos ver as opções de IFCONFIG no `man ifconfig`

```
Name
     ifconfig - configure a network interface
```

* De acordo com o manual, vemos que precisamos da flag [OPTION] `-a`
porque `if a single -a argument is given, it displays the status of all interfaces, even those that are down.`
* Agora, teste o `ifconfig -a`, dependendo do seu output, os comandos a seguir podem precisar de alguns ajustes.

#### Aqui estão algumas maneiras:

* __grep__. Existem várias expressões regulares que resolvem nosso problema. Aqui, procuramos por 5 repetições de 2 letras ou números seguidos por dois pontos, depois dois caracteres.
1. **-i** torna a busca case insensitive (não difere maiúsculas e minúsculas)
2. **-o** faz com que o comando `grep` imprima apenas a parte correspondente.
3. **-E** permite expressões regulares estendidas.
```
ifconfig -a | grep -ioE '([a-z0-9]{2}:){5}..'
```

* __sed__.
1. **-n** suprime a saída normal
2. **-r** permite expressões regulares estendidas.

Usando o mesmo regex acima, esse script tentará substituir tudo na linha pela parte que corresponda ao regex. Se a substituição foi bem-sucedida, a linha resultante é impressa (por causa do p no final da substituição).
```
ifconfig -a | sed -rn 's/.*(([a-z0-9]{2}:){5}..).*/\1/p'
```

* __awk__. Se a linha começar com um caractere de palavra ([a-zA-Z0-9_]) e tiver 5 campos, imprima o último.
```
ifconfig -a | awk '/^\w/&&NF==5{print $NF}'
```

* __Perl__. Há mais de uma maneira de fazer isso, utilizando a mesma lógica do awk acima.
```
ifconfig -a | perl -lane 'if(/^\w/&&$#F==4){print $F[$#F]}'
```

* __Coreutils__.
```
LANG_ALL=C ifconfig -a | grep 'ether' | tr -s ' ' '\t' | cut -f 3
```
OU
```
LANG_ALL=C ifconfig -a | grep 'HWadd' | tr -s ' ' '\t' | cut -f 5
```

> Parece monstruoso, mas no final, podemos misturar os conceitos e chegar a uma maneira simplificada, por exemplo:

```
ifconfig -a | grep ether | awk '{print $2}'
```

Os endereços ficam ao lado da palavra "ether", então a opção `grep` devolve a linha em que essa palavra está e, em seguida, o awk printa o segundo grupo de palavras, um por linha, que são os endereços MAC.

------------------------------------------
### [back](https://github.com/hana42/42piscine/tree/master/Shell01)
