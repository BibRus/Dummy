## Лабораторные работы [ Основы Git ]  

### Версия и конфигурация Git

```
Microsoft Windows [Version 10.0.19044.1706]
(c) Корпорация Майкрософт (Microsoft Corporation). Все права защищены.

C:\Users\BibRus> git --version
git version 2.35.1.windows.2

C:\Users\BibRus> git config -l
diff.astextplain.textconv=astextplain
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
http.sslbackend=openssl
http.sslcainfo=C:/Program Files/Git/mingw64/ssl/certs/ca-bundle.crt
core.autocrlf=true
core.fscache=true
core.symlinks=false
core.editor="C:\\Program Files\\Notepad++\\notepad++.exe" -multiInst -notabbar -nosession -noPlugin
pull.rebase=false
credential.helper=manager-core
credential.https://dev.azure.com.usehttppath=true
init.defaultbranch=master
user.name=BibRus
user.email=bibaevsurlan@gmail.com

C:\Users\BibRus>
```

### Примечание

> Лабораторные работы я делал в конце марта, но только сейчас я отправляю результат выполнения. Выполнял я до того, как вы сказали выполнить их, делая снимки экрана. У меня сохранился только один снимок с камеры смартфона, то как я делал третью лабораторную работу, показывал для друга, но сохранил весь текст с командной строки. В третьей лабораторной работе выбрал второй вариант, так как я на втором месте по списку. Последнюю седьмую работу не смог в точности повторить, — вместо вашего репозитория [ [KEI_test](https://github.com/Radikot/KEI_test.git) ] я сделал копию своего, когда-то загруженного для предмета "Основы алгоритмизации и программирования" [ [Задачи по Python](https://github.com/BibRus/PythonTasks.git) ]. Вместо директории `C://ISD-11/BRR` я использовал `C:\Users\BibRus\Development\Projects\Local\Git\Dummy`


### Фотография с камеры смартфона
<img src="https://drive.google.com/uc?export=view&id=1OXVCW6JX4E1zGmdvY721vxB5yHzxoXTO" width="1200">
     
### Фотография с галереи смартфона
<img src="https://drive.google.com/uc?export=view&id=1C3u1mj3dWmIw8tLoD_FN0t-MGMYICmJl" width="1200">

### Лабораторная работа №1 «Первоначальная настройка Git»

```
Microsoft Windows [Version 10.0.19044.1586]
(c) Корпорация Майкрософт (Microsoft Corporation). Все права защищены.

C:\Users\BibRus> cd C:\Users\BibRus\Development\Projects\Local\Git\Dummy

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git init
Initialized empty Git repository in C:/Users/BibRus/Development/Projects/Local/Git/Dummy/.git/

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git add my_first_file.txt

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git commit
[master (root-commit) 1c50e19] Added my_first_file.txt
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 my_first_file.txt

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   my_first_file.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        my_second_file.txt

no changes added to commit (use "git add" and/or "git commit -a")

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git add my_second_file.txt

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git commit
[master 8e1171f] Added my_second_file.txt, my_first_file.txt changed
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 my_second_file.txt

C:\Users\BibRus\Development\Projects\Local\Git\Dummy>
```


### Лабораторная работа № 2 «Игнорирование, сравнение, удаление и перемещение файлов»

```
Microsoft Windows [Version 10.0.19044.1586]
(c) Корпорация Майкрософт (Microsoft Corporation). Все права защищены.

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git add .gitignore

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git commit
[master 6c8e37d] Added .gitignore
 1 file changed, 2 insertions(+)
 create mode 100644 .gitignore

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git add my_first_file.txt

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git diff
diff --git a/my_first_file.txt b/my_first_file.txt
index 816acc5..08b1dcc 100644
--- a/my_first_file.txt
+++ b/my_first_file.txt
@@ -1,2 +1,3 @@
 test row
-row to index
\ No newline at end of file
+row to index
+row no index
\ No newline at end of file

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git commit
[master b6a0dee] my_first_file.txt deleted
 1 file changed, 2 insertions(+)

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git commit
On branch master
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   my_first_file.txt
        deleted:    my_second_file.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        log/

no changes added to commit (use "git add" and/or "git commit -a")

C:\Users\BibRus\Development\Projects\Local\Git\Dummy>
```


### Лабораторная работа №3 «Просмотр истории коммитов»

```
Microsoft Windows [Version 10.0.19044.1586]
(c) Корпорация Майкрософт (Microsoft Corporation). Все права защищены.

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git log --pretty=format:"%h, %an, %s"
b6a0dee, BibRus, my_first_file.txt deleted
6c8e37d, BibRus, Added .gitignore
8e1171f, BibRus, Added my_second_file.txt, my_first_file.txt changed
1c50e19, BibRus, Added my_first_file.txt

C:\Users\BibRus\Development\Projects\Local\Git\Dummy>
```

### Лабораторная работа №4 «Отмена изменений. Работа с метками» 


```
Microsoft Windows [Version 10.0.19044.1586]
(c) Корпорация Майкрософт (Microsoft Corporation). Все права защищены.

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git add 1.txt

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git commit
[master 007b0ca] add txt file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 1.txt

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git add 2.txt

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git add 3.txt

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git reset 2.txt
Unstaged changes after reset:
M       my_first_file.txt
D       my_second_file.txt

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git commit --amend
[master 4d741da] add 1.txt and 3.txt
 Date: Thu Mar 24 17:02:50 2022 +0300
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 1.txt
 create mode 100644 3.txt

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git tag -a V0.01

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git log --pretty=oneline
4d741da2e1ca5d398466d1ad29a7fa913cf7ebaf (HEAD -> master, tag: V0.01) add 1.txt and 3.txt
b6a0dee3f06f03fb40a2d6eb44346d87c01fdf24 my_first_file.txt deleted
6c8e37d008b132b6f0ac77e9d5e7ccd3c70cc003 Added .gitignore
8e1171f496d29b89f7c7648c892ddd5c030ce283 Added my_second_file.txt, my_first_file.txt changed
1c50e199b55d7d9efa71f9e95511cd4be9b81833 Added my_first_file.txt

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git tag vl-1 1c50e199b55d7d9efa71f9e95511cd4be9b81833

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git tag
V0.01
vl-1

C:\Users\BibRus\Development\Projects\Local\Git\Dummy>
```

### Лабораторная работа №5 «Ветвление. Конфликты»

```
Microsoft Windows [Version 10.0.19044.1586]
(c) Корпорация Майкрософт (Microsoft Corporation). Все права защищены.

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git branch my_first_branch

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git checkout my_first_branch
Switched to branch 'my_first_branch'
M       my_first_file.txt
D       my_second_file.txt

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git add in_branch.txt

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git commit
[my_first_branch 8f482d6] Added in_branch.txt
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 in_branch.txt

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git checkout master
Switched to branch 'master'
M       my_first_file.txt
D       my_second_file.txt

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git checkout -b new_branch
Switched to a new branch 'new_branch'

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git add 1.txt

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git commit
[new_branch eae5cb8] 1.txt changed
 1 file changed, 1 insertion(+)

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git checkout master
Switched to branch 'master'
M       my_first_file.txt
D       my_second_file.txt

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git merge my_first_branch
Updating 4d741da..8f482d6
Fast-forward
 in_branch.txt | 0
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 in_branch.txt

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git merge new_branch
Merge made by the 'ort' strategy.
 1.txt | 1 +
 1 file changed, 1 insertion(+)

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git branch -d my_first_branch
Deleted branch my_first_branch (was 8f482d6).

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git branch -d new_branch
Deleted branch new_branch (was eae5cb8).

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git branch branch_1

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git branch branch_2

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git checkout branch_1
Switched to branch 'branch_1'
M       my_first_file.txt
D       my_second_file.txt

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git add 1.txt

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git add 3.txt

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git commit
[branch_1 ca4a0a8] 1.txt and 3.txt changed
 2 files changed, 2 insertions(+), 1 deletion(-)

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git checkout branch_2
Switched to branch 'branch_2'
M       my_first_file.txt
D       my_second_file.txt

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git add 1.txt

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git add 3.txt

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git commit
[branch_2 0f7f10a] 1.txt and 3.txt changed in branch_2
 2 files changed, 2 insertions(+), 1 deletion(-)

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git checkout branch_1
Switched to branch 'branch_1'
M       my_first_file.txt
D       my_second_file.txt

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git merge branch_2
Auto-merging 1.txt
CONFLICT (content): Merge conflict in 1.txt
Auto-merging 3.txt
CONFLICT (content): Merge conflict in 3.txt
Automatic merge failed; fix conflicts and then commit the result.

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git add 1.txt\

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git reset 1.txt\
Unstaged changes after reset:
U       1.txt
U       3.txt
M       my_first_file.txt
D       my_second_file.txt

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git add 1.txt

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git commit
error: Committing is not possible because you have unmerged files.
hint: Fix them up in the work tree, and then use 'git add/rm <file>'
hint: as appropriate to mark resolution and make a commit.
fatal: Exiting because of an unresolved conflict.
U       3.txt

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git add 3.txt

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git commit
[branch_1 bb120f4] Merge branch 'branch_2' into branch_1

C:\Users\BibRus\Development\Projects\Local\Git\Dummy>
```

### Лабораторная работа №6 «Сокрытие»

```
Microsoft Windows [Version 10.0.19044.1586]
(c) Корпорация Майкрософт (Microsoft Corporation). Все права защищены.

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git branch --merged
* branch_1
  branch_2
  master

C:\Users\BibRus\Development\Projects\Local\Git\Dummy>  git checkout master
Switched to branch 'master'
M       my_first_file.txt
D       my_second_file.txt

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git branch -d branch_1 branch_2
error: The branch 'branch_1' is not fully merged.
If you are sure you want to delete it, run 'git branch -D branch_1'.
error: The branch 'branch_2' is not fully merged.
If you are sure you want to delete it, run 'git branch -D branch_2'.

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git checkout -b work
Switched to a new branch 'work'

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git stash
Saved working directory and index state WIP on work: bd68c93 Merge branch 'new_branch'

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git stash apply --index
Removing my_second_file.txt
On branch work
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   1.txt
        modified:   my_first_file.txt
        deleted:    my_second_file.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        2.txt
        log/

no changes added to commit (use "git add" and/or "git commit -a")

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git add 1.txt 2.txt

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git checkout -b new_branch
Switched to a new branch 'new_branch'

C:\Users\BibRus\Development\Projects\Local\Git\Dummy> git commit
[new_branch 53d1988] 1.txt and 2.txt changed
 2 files changed, 2 insertions(+), 1 deletion(-)
 create mode 100644 2.txt

C:\Users\BibRus\Development\Projects\Local\Git\Dummy>
```

### Лабораторная работа №7 «Работа с удаленным репозиторием»

```
Microsoft Windows [Version 10.0.19044.1586]
(c) Корпорация Майкрософт (Microsoft Corporation). Все права защищены.

C:\Users\BibRus> ssh-keygen
Generating public/private rsa key pair.
Enter file in which to save the key (C:\Users\BibRus/.ssh/id_rsa):
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in C:\Users\BibRus/.ssh/id_rsa.
Your public key has been saved in C:\Users\BibRus/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:KCZHjfP23/UKd1bnqd9hUDHCBYSyTrHHcT5/9hK/Sag bibrus@Workbook
The key's randomart image is:
+---[RSA 3072]----+
|            ++o+ |
|     o   o o o. o|
|    + .   * +  . |
|   . o . + o o.  |
|  . + + S .  .o o|
|   + o . .    +o*|
|        .   ..oO*|
|         . ..+=+*|
|          .E..o*+|
+----[SHA256]-----+

C:\Users\BibRus>




Microsoft Windows [Version 10.0.19044.1586]
(c) Корпорация Майкрософт (Microsoft Corporation). Все права защищены.

C:\Users\BibRus> cd C:\Users\BibRus\Development\Projects\Local\Git

C:\Users\BibRus\Development\Projects\Local\Git> git clone git@github.com:BibRus/PythonTasks.git
Cloning into 'PythonTasks'...
The authenticity of host 'github.com (140.82.121.4)' can't be established.
ED25519 key fingerprint is SHA256:+DiY3wvvV6TuJJhbpZisF/zLDA0zPMSvHdkr4UvCOqU.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added 'github.com' (ED25519) to the list of known hosts.
remote: Enumerating objects: 49, done.
remote: Counting objects: 100% (49/49), done.
remote: Compressing objects: 100% (37/37), done.
remote: Total 49 (delta 5), reused 49 (delta 5), pack-reused 0
 KiB | 102.00 KiB/s
Receiving objects: 100% (49/49), 88.60 KiB | 118.00 KiB/s, done.
Resolving deltas: 100% (5/5), done.

C:\Users\BibRus\Development\Projects\Local\Git>
```
