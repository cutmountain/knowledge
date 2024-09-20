# Git & GitHub cheat sheet

>```console
>(base) me@pc REPOS % mkdir repo_prueba  
>(base) me@pc REPOS % cd repo_prueba  
>```
>```console
>(base) me@pc repo_prueba % git init  
>```

```
Initialized empty Git repository in /REPOS/repo_prueba/.git/
```


>```console
>(base) me@pc repo_prueba % touch README.md
>```


Add "README.md" file to git's _**staging area**_:

>```console
>(base) me@pc repo_prueba % git add README.md
>```


Tell git to commig everything in the _**staging area**_ (n.b. This will create a _**point in time**_ in the history of your current branch):

>```console
>(base) me@pc repo_prueba % git commit -m "Primer commit"
>```
```
Author identity unknown

*** Please tell me who you are.

Run

  git config --global user.email "you@example.com"
  git config --global user.name "Your Name"

to set your account's default identity.
Omit --global to set the identity only in this repository.

fatal: unable to auto-detect email address (got 'me@pc.(none)')
```

>```console
>(base) me@pc repo_prueba % git config --global user.email email-of-your-GitHub-account@mail.com
>```console
>```
>(base) me@pc repo_prueba % git config --global user.name your-GitHub-username
>```

      
>```console
>(base) me@pc repo_prueba % git commit -m "Primer commit"     
>```
```
[main (root-commit) 7d39731] Primer commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 readme.md
(base) me@pc repo_prueba % git log    
commit 7d39731b200df9b641050657a4983d44605a8b41 (HEAD -> main)
Author: your-GitHub-username <email-of-your-GitHub-account@mail.com>
Date:   Thu Sep 12 11:55:54 2024 +0200

    Primer commit
```

>```console
>(base) me@pc repo_prueba % touch file1.md
>(base) me@pc repo_prueba % git add file1.md
>(base) me@pc repo_prueba % git commit -m "Segundo commit"
>```
```
[main 91a9906] Segundo commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 file1.md
``` 

>```console
>(base) me@pc repo_prueba % touch file2.md
>(base) me@pc repo_prueba % git add file2.md
>(base) me@pc repo_prueba % git commit -m "Tercer commit"
>```
```
[main d3b52a3] Tercer commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 file2.md
```


>```console
>(base) me@pc repo_prueba % git log
>```
```
commit d3b52a36bfeb9c31beab07a1c44b41e9cce16736 (HEAD -> main)
Author: your-GitHub-username <email-of-your-GitHub-account@mail.com>
Date:   Thu Sep 12 12:44:36 2024 +0200

    Tercer commit

commit 91a9906165625b9c69d0bc4b1ade6396b4c37ee1
Author: your-GitHub-username <email-of-your-GitHub-account@mail.com>
Date:   Thu Sep 12 12:43:18 2024 +0200

    Segundo commit

commit 7d39731b200df9b641050657a4983d44605a8b41
Author: your-GitHub-username <email-of-your-GitHub-account@mail.com>
Date:   Thu Sep 12 11:55:54 2024 +0200

    Primer commit
```

Check your remote **references**:

>```console
>(base) me@pc repo_prueba % git remote 
>```

Add a reference to a remote origin and name it (typically) "origin":
>```console
>(base) me@pc repo_prueba % git remote add origin https://github.com/your-github-username/repo_prueba.git
>```

Check again your remote **references**:
>```console
>(base) me@pc repo_prueba % git remote
```
origin
```

Check your **local** branches (* indicates the branch you are in --i.e.current **local** branch--):

>```console
>(base) me@pc repo_prueba % git branch
```
* main
```

Push your commited changes in your _local_ repository to the _remote_ repository (option -u sets your current _local_ branch to track the _remote_ --i.e. upstream-- "main" branch in your remote reference "origin"):

>```console
>(base) me@pc repo_prueba % git push -u origin main
>```
```
Username for 'https://github.com': your-github-username
Password for 'https://your-github-username@github.com': GitHub-access-token-as-in-GitHub__Settings__Developer-Settings
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (5/5), 419 bytes | 419.00 KiB/s, done.
Total 5 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/your-github-username/repo_prueba
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.
```


Check that a _remote_ branch has been created with the same name as your _local_ branch:

>```console
>(base) me@pc repo_prueba % git branch -r
>```
```
  origin/main
```


>```console
>(base) me@pc repo_prueba % git status
>```
```
On branch main
Your branch is up to date with 'origin/main'.
nothing to commit, working tree clean
```

Grab changes made in the _remote_ repository:

>```console
>(base) me@pc repo_prueba % git pull origin
>```
```
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (3/3), 935 bytes | 187.00 KiB/s, done.
From https://github.com/your-github-username/repo_prueba
   51d6264..da8d7b4  main       -> origin/main
Updating 51d6264..da8d7b4
Fast-forward
 file3.md | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 file3.md
```

Notice there's no need to specify the name of the branch anymore when doing pull/push as local branch main was set to track upstream branch origin/main with the -u option previously.


