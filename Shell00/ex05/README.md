### [back](https://github.com/hana42/42piscine/tree/master/Shell00)

------------------------------------------
#### Objetivo:
Criar um programa shell que retorne os id dos últimos 5 commits do seu repositório git.
```
$ bash git_commit.sh | cat -e
```
-----------------------------------------
###  Shell script
Ao escrever um script (coleção de comandos unix), você tem a opção de especificar qual shell pode ser usado. Geralmente, você precisa definir qual Shell será usado do código, dizendo ao sistema para usá-lo ao rodar o programa.

Por exemplo: `#!/bin/sh`

####  O programa

```
#!/bin/sh
git log --format=%H -n5
  ↑         ↑     ↑  ↑
  │         │     │  └─── -<n> Mostra apenas os últimos n commits
  │         │     └───── %H mostra a hash do commit
  │         └─────── --format=<format> Formata os logs da forma desejada
  └────────────── Por padrão, sem argumentos, o git log lista os commits em ordem cronológica inversa;
  Isto é, os commits mais recentes aparecem primeiro com o nome e email do autor, data e mensagem de commit.
```

> Para o arquivo ser executável, não se esqueça de atribuir a permissão a ele. E como citado nos exercícios anteriores, o comando chmod se encarrega disto:
`$ chmod +x arquivo`
Pronto, o arquivo poderá ser executado com um “./arquivo”


------------------------------------------
### [back](https://github.com/hana42/42piscine/tree/master/Shell00)
