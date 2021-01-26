# Git Tutorial

- [Git Download](https://git-scm.com/downloads)
- [Visual Studio Code](https://code.visualstudio.com/) - My preferred IDE for any programming language with git integrated

## Getting Started

0. Ensure you are in a new, clean directory with a `README.md` file

1. Create repo
    ```bash
    git init
    ```
2. Set branch name to "master" or whatever branch name you want
    ```bash
    git branch -m master
    ```
3. Set origin to GitHub repository. Where `<url>` is the URL of your git repository.
    ```bash
    git remote add origin <url>
    ```
4. Add files to commit
    ```bash
    git add .
    ```
5. Commit the files
    ```bash
    git commit -m "init"
    ```
6. Intial push. Ensure you are pushing to the name you gave to remote and the branch name you set. In this example the remote name is "origin" and the branch name is "master"
    ```bash
    git push -u origin master
    ```

## Workflow

The philosiphy of git is to seperate your code changes into small, readable commits. You may stack up as many commits locally as you like, and push them when you are ready.

### Typical Workflow

1. Make some changes to code/files
2. Add them. You can do `git add <file>` individually instead.
    ```bash
    git add . 
    ```
3. Commit you changes and annotate what you changed
    ```bash
    git commit -m "<DESCRIBE YOUR CHANGES>"
    ```
4. Repeat steps 1 - 3 until you want to update remote repository
5. Push commits. If you are pushing a branch that does not exist remotely, you will need to `git push -u origin <branch>`
    ```bash
    git push
    ```

## Common Git commands

### Initializes repository
```bash
git init
```

<br/>

### Clones repository into a folder
```bash
git clone <url>
```

<br/>

### Pull latest commits from repository
```bash
git pull # -r
```
#### Most Used Options
- `-r` rebase all local commits on top commits pulled from repo

<br/>

### Push all local commits to the remote repository
```bash
git push
```
#### Most Used Options
- `--set-upstream origin <branch>`/`-u origin <branch>` Pushes branch to remote

### Stage changes to be committed
```bash
git add <files>
```
#### Most Used Options
- `-a` will stage all files

<br/>

### Commit all staged changes
This will open a text editor to briefly describe your changes.

```bash
git commit
```
#### Most Used Options
- `-m "<message>"` Passes message rather than opening a text editor
- `--amend` Adds staged changes to the previous commit

<br/>

### List all branches
```bash
git branch <name>
```
If you include a name, it will create a new branch with that name from your currently active branch.
#### Most Used Options
- `-a` Lists all local and remote branches
- `-d <branch>` Deletes a branch
- `-m <branch>` Renames a branch

<br/>

### Switch to a branch
Should commit all changes before checking out.

```bash
git checkout <branch>
```
#### Most Used Options
- `-b` Creates and switches to a new branch

<br/>

### Resets all commit to HEAD
```bash
git reset
```
#### Most Used Options
- `HEAD~1` Undos last commit
- `--hard` Deletes all local changes

### Log commits
```bash
git log
```
#### Most Used Options
- `--pretty=oneline` prints everything nicely in one line

<br/>

---

## Useful Aliases

Aliases are essentially custom git commands that are defined in `C:\Users\%USER%\.gitconfig`

```
[alias]
    co = checkout
    lg = log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit
    undo = reset HEAD~1 --mixed
    amend = commit -a --amend
```
