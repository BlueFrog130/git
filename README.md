# Git Tutorial

### Todo List

- [X] Install git
- [X] Create new GitHub repository
- [X] Initialize git repository
- [X] Set remote branch to GitHub repo
- [ ] Creating new files & commit them
- [ ] Create new branch
- [ ] Merge conflicts
- [ ] .gitignore

## Git commands
---

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