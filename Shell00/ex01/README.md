### [back](https://github.com/hana42/42piscine/tree/master/Shell00)

------------------------------------------
#### Objetivo:
```
$ ls -l
total XX
-r--r-xr-x 1 XX XX 40 Jun 1 23:42 testShell00
```

------------------------------------------
#### Tamanho do arquivo = 40
Para criar o arquivo `testDay00` nós podemos abrir qualquer editor de texto
como o `vim, atom, VScode etc` e adicionar `40` caracteres/símbolos.
> Cada caractere (seja espaço, simbolo ou letra) adiciona 1 byte

------------------------------------------
#### Mudar datas e horários
Usando o comando [TOUCH](https://linux.die.net/man/1/touch):
```
$ touch -a -m -t 202406012342.00 arquivo.ext
```
Onde:
```
-a = acessado
-m = modificado
-t = tempo - utilize o formato [[CC]YY]MMDDhhmm[.ss]
```

------------------------------------------
#### Mudando as permissões de arquivo com o comando [CHMOD](https://en.wikipedia.org/wiki/Chmod)
O comando chmod é utilizado para modificar as permissões de um arquivo.
Para utilizá-lo, existem duas formas:

```
     chmod        permissões         nome do arquivo
           [quem][ação][permissão]
```

```
      quem            ação          permissão

     u = user        + = add         r = read
     g = group       - = remove      w = write
     o = other                       x = execute
     a = all
```


As permissões de cada arquivo do diretório são mostradas utilizando o comando ls -l. Dessa forma:

```
     user read (r)
     user write (w)
     user execute (x)
        group read (r)
        group write (w)
        group execute (x)
           others read (r)
           others write (w)
           others execute (x)
```
> Que aparecem como:        -rwxrwxrwx

### Exemplo:
```
chmod u+x arquivo.ext
```
Adiciona a permissão para executar ao user (você).

### OU

| Bin |        Permissão        |  rwx  |
| --- |:-----------------------:| -----:|
|  7  | read, write and execute |  rwx  |
|  6  | read and write          |  rw-  |
|  5  | read and execute        |  r-x  |
|  4  | read only               |  r--  |
|  3  | write and execute       |  -wx  |
|  2  | write only              |  -w-  |
|  1  | execute only            |  --x  |
|  0  | none                    |  ---  |

### Exemplo:
```
chmod 777 arquivo.ext
```
Adiciona a permissão de ler, escrever e executar a todos.


------------------------------------------
Para mais detalhes, consulte o manual:
```
$ man chmod
```



Após resolver o execício, execute o comando
`tar -cf testShell00.tar testShell00`

------------------------------------------
### [back](https://github.com/hana42/42piscine/tree/master/Shell00)
