### [back](https://github.com/hana42/42piscine/tree/master/Shell00)

------------------------------------------
#### Objetivo:
* Crie um arquivo mágico chamado **ft_magic** que será formatado para detectar arquivos de tipo **42 file**, constituído por uma string "42" no 42º byte.

```
$ man file
```
-----------------------------------------

#### Para criar nosso arquivo mágico (ft_magic) precisamos que:
* O arquivo seja formatado corretamente para detectar arquivos de tipo **42 file**:
* Esse tipo de arquivo é constituído por uma string "42" no 42º byte.
* Se utilizarmos o `man magic` teremos a seguinte formatação:
```
41 string  42  42 file
└┬┘└─┬──┘ └─┬┘└───┬───┘
 │   │      │     └─── Mensagem a ser impressa.
 │   │      └───────────── Teste a ser realizado, valor a ser comparado com o arquivo.
 │   └────────────────────── Tipo dos dados a serem testados.
 └─────────────────────────── Número que especifica o deslocamento, em bytes, dentro do arquivo a ser testado.
 Utilizamos 41 para que o número "42" termine no 42º byte.
```


> Você precisará de um arquivo de tipo 42 file para teste, para isso, crie qualquer arquivo de texto que possua "42" no 42º byte ou baixe o anexo "42file"


------------------------------------------
### [back](https://github.com/hana42/42piscine/tree/master/Shell00)
