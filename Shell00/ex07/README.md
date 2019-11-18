#### Objetivo:
* Criar o arquivo **b** conforme:
```
diff a b > sw.diff
```
#### RTFM!
------------------------------------------
### Comando diff
O comando `diff` examina duas versões diferentes de um arquivo e lista as diferenças entre elas. As diferenças podem ser armazenadas em um arquivo chamado patch file.

De acordo com a [Wikipedia](https://pt.wikipedia.org/wiki/Diff):
```
Diff é um utilitário de comparação de arquivos que gera as diferenças entre dois arquivos. É normalmente usado
para mostrar as mudanças entre uma versão de um arquivo e a versão anterior do mesmo arquivo. O diff mostra as
alterações realizadas por linha para arquivos de texto. Implementações modernas também suportam arquivos binários.
A saída é chamada de um "diff" ou um patch, uma vez que a saída pode ser aplicada com o programa patch do Unix.
```

### Comando patch
O comando `patch` pode ler um arquivo de patch e usar o conteúdo como um conjunto de instruções. Seguindo essas instruções, ele aplica as diferenças textuais entre dois programas ou arquivos.
Uma vez que você tem alguma das versões dos arquivos, você consegue transformar uma na outra, e vice versa.
O patch é muito utilizado em processos de software para clarificar o que um programador modificou, diferenciando o código dele do código do repositório (anterior a mudança dele). Isso facilita o processo de revisão.

* fun fact:
O programa patch original foi escrito por Larry Wall, que foi também o autor da linguagem de programação Perl.

## Chegando ao resultado

Considerando que já temos o arquivo `sw.diff`:

```
$ patch -o b a sw.diff
```

* Seu arquivo `b` deverá ser assim:
```
Episode V, A NEW H0PE It is a period of civil war
Rebel spaceships, striking from a hidden base, have won their first victory against the evil Galactic Empire.
During the battle, Rebel spies managed to steal secret plans to the Empire's ultimate weapon, the STAR DEATH, an
armored space station with enough power to destroy an entire planet.


Pursued by the Empire's sinister agents,
Princess Mehdi races home aboard her starship, custodian of the stolen plans that can save her people and restore
the dictatorship to the galaxie..
```

------------------------------------------
### [back](https://github.com/hana42/42piscine/tree/master/Shell00)
