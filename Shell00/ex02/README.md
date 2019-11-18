### [back](https://github.com/hana42/42piscine/tree/master/Shell00)

------------------------------------------
#### Objetivo:
Crie os seguintes arquivos e diretórios. Faça o que for necessário para que, quando você use o comando ls -l em seu diretório, o output fique assim:
```
$ ls -l
total 42
drwx--xr-x 2 login wheel XX	Jun 1 20:47 test0
-rwx--xr-- 1 login wheel 4	Jun 1 21:46 test1
dr-x---r-- 2 login wheel XX	Jun 1 22:45 test2
-r-----r-- 2 login wheel 1	Jun 1 23:44 test3
-rw-r----x 1 login wheel 2	Jun 1 23:43 test4
-r-----r-- 2 login wheel 1	Jun 1 23:44 test5
lrwxr-xr-x 1 login wheel 5	Jun 1 22:20 test6 -> test0
$
```

__Notas__: "login" e "wheel" serão substituídos, respectivamente, por seu login e seu grupo.

Seu output não terá "total 42", como mostrado no exemplo.

Não se preocupe com o que tem no lugar de "XX".

* Quando terminar, execute o comando `$ tar -cf exo2.tar *` para criar o arquivo a ser enviado e exclua os arquivos restantes da pasta.
------------------------------------------
#### Explicação do output do comando `ls -l`
```
-rwxrw-r-- 10   root   root 2048  Nov 14 16:25 arquivo.ext
?UUUGGGOOO 00  UUUUUU GGGGGG ####  └─ Data e nome do arquivo
↑ ↑  ↑  ↑   ↑     ↑      ↑    ↑
│ │  │  │   │     │      │    └─── Tamanho do arquivo
│ │  │  │   │     │      └──────── Nome do grupo (Usuário, Administrador, etc)
│ │  │  │   │     └─────────────── Proprietário
│ │  │  │   └────────────────────── Contagem de links (o que constitui um "link" aqui varia)
│ │  │  │
│ └──┴──┴───────────────────────────── Permissão de leitura, modificação e execução para [U]ser, [G]roup, and [O]thers (todo os outros)
└───────────────────────────────────── Tipo de arquivo -
```
>As flags de permissões (UUUGGGOOO) são três conjuntos, em que o primeiro
conjunto é "User" (ou seja, proprietário), o segundo conjunto é "Group" e
o terceiro o conjunto é "Others" (qualquer um que não seja proprietário nem grupo).

------------------------------------------
#### Como criar

> * Lembre-se de que usamos `touch` e `mkdir` para criar arquivos e pastas,
respectivamente.

Agora, para a parte nova: nós precisamos criar um _soft link_ para a pasta `test0`
> É isso que o símbolo `->` significa.

E se prestarmos atenção aos detalhes, notamos que `test5` é um __hard link__
do arquivo `test3`
> Determinamos isso devido ao tamanho da contagem de links em ambos os arquivos, além do fato de que eles compartilham a mesma data

Para uma ideia de qual a diferença entre __hard__ e __soft__ links nós podemos seguir essa imagem:

![linktypes](https://raw.githubusercontent.com/idevHive/42/master/Piscines/C/Day00/resources/picts/hard-link_vs_soft-link.jpg "Hard Link vs Soft Link")

Como chegamos a esse quadro:
1. Criamos um arquivo que apontará para um novo inode, exemplo:
`$ touch myfile.txt`
2. Criamos um hard link para o arquivo `myfile.txt` chamado `my-hard-link`:
`$ ln myfile.txt my-hard-link`
3. Criamos um soft link chamado `my-soft-link` para o arquivo `myfile.txt`:
`$ ln -s myfile.txt my-soft-link`


O que acontecerá se o `myfile.txt` for excluído (ou movido):
`my-hard-link` ainda apontará para o mesmo conteúdo e, portanto, não é afetado, enquanto
O `my-soft-link` agora não apontará para nada.

------------------------------------------
#### Mudando a data de um symlink
Nós apenas precisamos adicionar a flag -h ao `touch`
```
touch -h -a -m -t 201806012220.00 test6
```
> Utilize `man touch` para mais informações.
------------------------------------------
### [back](https://github.com/hana42/42piscine/tree/master/Shell00)
