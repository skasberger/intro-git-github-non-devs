Intro Versioning with Git/GitHub for non-developer
==============================

Introduction into Versioning of text-based Files with Git and GitHub at the Semantic Media Wiki Conference at 1. of October 2014 in Vienna.

At the beginning there was a small introductory presentation in software-versioning, git and github, before the practical part to use git and github for management of data and textfiles started.

## Introduction
Create folder.
```shell
mkdir test
cd test
```

### Create Repo
Create Git repository.
```shell
git init
git status
```
Check .git folder.

Create file.
```shell
touch profil.txt
git status
```

### DATEIEN HINZUFÜGEN
Stage file for commit.
```shell
git add profil.txt
git status
```
Unstage file.
```shell
git reset
git status
```
Remove file out of repo.
```shell
git rm --cached profil.txt
git add profil.txt
git status
```

### Commit changes
A commit is the creation of a static state of the repository (snapshot), which can be re-established whenever wanted.
```shell
git commit -m"create profil.txt"
git status
git log 
```

### Delete file
Remove file from repository and filesystem.
```shell
git rm profil.txt
git status
```

### Walk through history
Switch between commits.
```shell
git checkout <COMMITHASH>
git checkout master
```

### Check Diff's
Create and add new file.
```shell
touch data.csv
git add data.csv
git commit -m"create data.csv"
```
Add lines to file.
```text
name;age;profession
stefan;30;student
sabine;28;designer

```
Add update.
```shell
git add data.csv
git commit -m"edit data.csv"
git status
```
Add lines to file.
```text
manuel;45;painter

```
View changes in file.
```shell
git diff --unstaged data.csv
git commit -m"update data.csv"
git status
git log
git lol
```

### Reverse changes
Add lines to file.
```text
sue;55;researcher

```
Discard changes of file back to HEAD.
```shell
git reset HEAD data.csv
git checkout -- data.csv
git status
```

### BRANCHEN
View branches.
```shell
git branch -v
```
Create devel branch.
```shell
git branch devel
git branch -v
git status
```
Copy GeoJSON file.

```shell
cp ../map.geojson .
git status
```
Add GeoJSON file to repo.
```shell
git add map.geojson
git commit -m"add map.geojson"
```
Change branch -> master
```shell
git checkout master
git status
```
### MERGEN
Add lines to file.
```text
peter;12;

```
Add changes.
```shell
git add data.csv
git commit -m"add banker to data.csv"
git status
```
Merge master-branch with devel-branch.
```shell
git merge devel
git checkout devel
git lol
```

### Create Repo at GitHub
View remotes.
```shell
git remote -v
```
Create repo.
```shell
git remote add origin XXXX
git remote -v
git status
```

### Upload local repot to GitHub 
Upload local repo to GitHub.
```shell
git pull origin master
```

### Download repo from GitHub
Download repo on GitHub to local drive.
```shell
git clone <REPOURL>
```

### Sync repo
Syncronize local repo with original GitHub repo.
```shell
git fetch 
```

### Further
Help:
```shell
git help
```

## Sources
- [git](http://git-scm.com/)
- [GitHub](https://github.com)
- [GitHub Flavored Markdown](https://help.github.com/articles/github-flavored-markdown)
- [Buch: Pro Git](http://git-scm.com/book/de)

## FAQ

### How often should I commit?
**After every relevant change or when you finished a certain part.**

### What should I write into the Commit-Message?
**As much as you need in two years to fully understand, what was done in the changes. English and present tense is recommended.**



