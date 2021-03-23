**Entenda o repositorio**

Baixe o arquivo [handson.zip] (handson.zip) e descompacte-o A pasta handson é um repositório git. Usando a linha de comando, altere o diretório para "handson/"

As caixas vazias representam o conteúdo que você precisa preencher e postar em seu repositório privado

*1. Descreva qual é a saída dos seguintes comandos*
git branch
git checkout BRANCH_NAME (USE THE NAME OF AN EXISTING BRANCH)
git log --decorate

```
Resposta: o primeiro comando apresenta as branchs exitentes. O segundo comando muda pra branch (no nosso exemplo: feature-foo ) e o terceiro mostra o log dessa branch
```



*2. Tente usar git log --graph --all. O que acontece?*
```
Resposta: vai mostrar a linha do tempo dos commits, apresentando cada branch que foi criada e cada commit. 


PS C:\Users\hhfs\Desktop\test\handson\handson> git log --graph --all
* commit f67f266cf420735187053f10d32e2c0f7cbc5a43 (master)
| Author: Igor Steinmacher <igorsteinmacher@gmail.com>
| Date:   Fri Aug 24 15:30:05 2018 -0700
|
|     Adding class B skeleton
|
| * commit a70a8e9d3c5390e367028faf033f2a9ef03d2e91 (HEAD -> feature-foo)
|/  Author: Igor Steinmacher <igorsteinmacher@gmail.com>
|   Date:   Fri Aug 24 15:29:22 2018 -0700
|
|       Adding header of method foo()
|
* commit 309b0d73ff9c2163591c9e96e307fe61b4c8f58a
| Author: Igor Steinmacher <igorsteinmacher@gmail.com>
| Date:   Fri Aug 24 15:27:16 2018 -0700
|
|     Adding class A skeleton
|
* commit 9c1eeb8901b0926ce7fa13cc6ce0a1876fc4179b
  Author: Igor Steinmacher <igorsteinmacher@gmail.com>
  Date:   Fri Aug 24 15:26:44 2018 -0700

      Creating all files (all empty)
```



*3. Use git diff BRANCH_NAME para ver as diferenças de um ramo e do ramo atual. Sumarize as diferenças do master e do outro ramo.*
```
Reposta: A diferença entre feature-foo e Master é que foi adicionado um método na classe A e na master tem o método B. 
```


*4. Escreva uma sequencia de comandos para mesclar o ramo não-master no master*
```
Reposta: 
	1) git checkout master
	2) git merge feature-foo 

```



*5. Escreva um comando (ou sequência) para (i) criar um novo ramo chamado math (do master) e (ii) mudar para este ramo*
```

Resposta: git checkout -b outra

```


*6. Edite B.java adicionando o código abaixo ao conteúdo do arquivo*
System.out.println("I know math, look:")
System.out.println(2+2)


*7. Escreva o comando (ou sequencia) para realizar o commit de suas mudanças*
```
	git add *
	git commit -m "adicionando linhas"
	git push
```



*8. Volte para o branch master e mude B.java adicionando o seguinte código-fonte (confirme sua mudança para master):*
System.out.println("Hello World")
```
	git checkout main
```



*9. Escreva uma sequência de comando para mesclar o branch math em master e descreva o que aconteceu*

```
	git checkout main
	git add *
	git commit -m 'gerando outra parte do B'
	git merge outra

PS C:\Users\hhfs\Desktop\test\sl_mestrado> git add *
PS C:\Users\hhfs\Desktop\test\sl_mestrado> git commit -m 'gerando outra parte do B'
[main 91acff7] gerando outra parte do B
 2 files changed, 51 insertions(+), 10 deletions(-)
PS C:\Users\hhfs\Desktop\test\sl_mestrado> git merge outra
Auto-merging Git Assignment.md
CONFLICT (content): Merge conflict in Git Assignment.md
Auto-merging B.java
CONFLICT (content): Merge conflict in B.java
Automatic merge failed; fix conflicts and then commit the result.
```



*10. Escreva um conjunto de comandos para abortar a mesclagem*
```
Resposta: git merge --abort
```



*10. Agora repita o item 9, mas prossiga com a mesclagem manual (Editando B.java). Todas as funções implementadas são necessárias. Explique o seu procedimento*
```
	git merge outro -> fazer o merge
	git status -> vai mostrar os status dos arquivos. Vai apresentar o conflito. Vou no código e altero
	git add *
	git commit -m "resolvendo conflito"
	git push
```

*11. Escreva um comando (ou conjunto de comandos) para prosseguir com a mesclagem e atualizar o branch master*
```
	git push
```