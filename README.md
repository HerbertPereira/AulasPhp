
1 - Verifique se seu nome e email estão configurados no Git. Execute:
git config --global user.email "seu_email"
git config --global user.name "seu_nome"

2 - Os comandos que compõe o processo para adicionar as mudanças ao repositório remoto são:
git add --all
git commit -m 'mensagem'
git pull origin master --allow-unrelated-histories
git push -u origin master

É importante executar esses comandos na ordem
Com esses procedimentos, conseguiremos adicionar nossos arquivos ao GitHub ou BitBucket
Bons estudos a todos :)

para atualizar um arquivo que foi alterado
C:\Cursos\PHP\PHP HCode\Projeto\AulasPhp>git pull origin master

alteração nova e empurrando para o servidor
C:\Cursos\PHP\PHP HCode\Projeto\AulasPhp>git add --all

C:\Cursos\PHP\PHP HCode\Projeto\AulasPhp>git commit -m "alteração nova"
[master 3d8dfa2] alteração nova
 1 file changed, 1 insertion(+), 1 deletion(-)

C:\Cursos\PHP\PHP HCode\Projeto\AulasPhp>git push origin master
To https://github.com/HerbertPereira/AulasPhp.git
 ! [rejected]        master -> master (non-fast-forward)
error: failed to push some refs to 'https://github.com/HerbertPereira/AulasPhp.git'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Integrate the remote changes (e.g.
hint: 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

atualização acima deu um conflito, como corrigir

C:\Cursos\PHP\PHP HCode\Projeto\AulasPhp>git pull origin master
From https://github.com/HerbertPereira/AulasPhp
 * branch            master     -> FETCH_HEAD
Auto-merging index.php
CONFLICT (content): Merge conflict in index.php
Automatic merge failed; fix conflicts and then commit the result

resultado do erro no editor,ou seja no index

<?php

<<<<<<< HEAD
echo "Hello World!!! aulas de php em breve<strong>LOJAS VIRTUAIS </strong>"
=======
echo "Meu programa <strong> HELLO Brazil </strong>";
>>>>>>> bcb2dc513e84f239b20aea3a502249893e73a71a

?>

precisa remover o conflito e escolher o que quer

<?php

echo "Hello World!!! aulas de php em breve<strong>LOJAS VIRTUAIS </strong>"

?>

C:\Cursos\PHP\PHP HCode\Projeto\AulasPhp>git add --all

C:\Cursos\PHP\PHP HCode\Projeto\AulasPhp>git commit -m "resolvi o conflito"
[master 047fe8a] resolvi o conflito

C:\Cursos\PHP\PHP HCode\Projeto\AulasPhp>git push origin master
Enumerating objects: 10, done.
Counting objects: 100% (10/10), done.
Delta compression using up to 4 threads
Compressing objects: 100% (5/5), done.
Writing objects: 100% (6/6), 618 bytes | 309.00 KiB/s, done.
Total 6 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), done.
To https://github.com/HerbertPereira/AulasPhp.git
   bcb2dc5..047fe8a  master -> master
