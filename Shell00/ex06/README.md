### [back](https://github.com/hana42/42piscine/tree/master/Shell00)

------------------------------------------
#### Objetivo:
Escrever um shell script que retornará os arquivos ignorados pelo seu repositório git.
```
$ bash git_ignore.sh | cat -e
```
-----------------------------------------
## Try at your own risk

Na 42SP, enviei meu arquivo da seguinte forma:
```
#!/bin/sh
git check-ignore *
```
Algumas pessoas passaram com esse mesmo comando, outras não. `¯\_(ツ)_/¯`

#### Explicação rápida sobre outras formas:

```
#!/bin/sh
git status --ignored -s | grep '!!' | cut -d ' ' -f 2
```

```
$ man grep
```
O comando `grep` (Globally Search a Regular Expression and Print) procura por padrões especificados pelo usuário dentro de arquivos de texto. Em outras palavras, você pode pesquisar por palavras ou padrões e as linhas que serão exibidas.

```
$ man cut
```
O comando cut pode ser usado para mostrar apenas seções específicas de um arquivo de texto ou da saída de outros comandos. Ele lê o conteúdo de um ou mais arquivos, ou a saída de comandos, e apresenta como resultado uma coluna.


------------------------------------------
> Para o arquivo ser executável, não se esqueça de atribuir a permissão a ele. E como citado nos exercícios anteriores, o comando chmod se encarrega disto:
`$ chmod +x arquivo`
Pronto, o arquivo poderá ser executado com um “./arquivo”

### [back](https://github.com/hana42/42piscine/tree/master/Shell00)
