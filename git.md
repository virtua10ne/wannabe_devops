## my Git and GitHub progress roadmap
https://roadmap.sh/git-github?s=64665133410780a6d9b83b17

## Docs
- Free MOOC (ru): https://practicum.yandex.ru/git-basics/  
- Git HowTo: https://githowto.com/  
- Lots of examples: https://antonz.org/git-by-example/  
- Git visual cheatsheet: https://ndpsoftware.com/git-cheatsheet.html
- GitHub Training Kit: https://training.github.com/
- Conventional commits: https://www.conventionalcommits.org/ru/v1.0.0/
- Dive deeper in git log: https://elijahmanor.com/blog/git-log
- All Git commands: https://git-scm.com/docs/git#_git_commands

## Practice
```bash
# for no pager
--no-pager

# support regexp
.gitignore

# global and current repo (repo im in) parameters
git config list --global
git config list

# generate key pair with the specified encryption algorithm (ed25519 is strong and keys are compact)
ssh-keygen -t ed25519 -C "youremail@mail"
# then add public key part to GitHub settings, and store private key part in ~/.ssh/ 
# Optionally, configure github host in ~/.ssh/config
Host github.com
  Hostname github.com
  IdentityFile /d/VMs/GH/keys/id_ed25519_gh
  #IdentityFile D:\VMs\GH\keys\id_ed25519_gh # both styles works
  IdentitiesOnly yes
# This steps allows you to use GitHub (push) without additional authentication.

# init local repo from scratch
git init

# clone AVAILABLE repo 
git clone git@github.com:virtua10ne/first-project.git
# or FORK to your account to make it available first, then clone

# link local repo to remote repo as "origin" (if not cloned, but inited)
git remote add origin git@github.com:virtua10ne/wannabe_devops.git

# show remote if linked 
git remote -v

# remove remote link
git remote rm origin 
 
# check if there is new (untracked) or modified files
git status
  Untracked: не добавленные в staging с помощью add или в .gitignore
  Changes not staged for commit: новые изменения файлов, уже добавленных в staging
  Changes to be committed: изменения добавленные в staging

git log
git log --oneline: short hash & message
git log -N: last N commits
[alias] # aliases for ~/.gitconfig for handy git log
  lg = lg1
  lg1 = lg1-specific --all
  lg2 = lg2-specific --all
  lg3 = lg3-specific --all

  lg1-specific = log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(auto)%d%C(reset)'
  lg2-specific = log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold cyan)%aD%C(reset) %C(bold green)(%ar)%C(reset)%C(auto)%d%C(reset)%n''          %C(white)%s%C(reset) %C(dim white)- %an%C(reset)'
  lg3-specific = log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold cyan)%aD%C(reset) %C(bold green)(%ar)%C(reset) %C(bold cyan)(committed: %cD)%C(reset) %C(auto)%d%C(reset)%n''          %C(white)%s%C(reset)%n''          %C(dim white)- %an <%ae> %C(reset) %C(dim white)(committer: %cn <%ce>)%C(reset)'
  
# add file, dir, or all to staging area
git add .: current dir
git add <file>: specific file
git add --all: all new or changed (unstaged)

# unstage file or dir
git restore --staged <file>
git restore --staged .

# restore changes in unstaged file to last commited version
git restore <file>
# if staged use `git restore --staged <file>` first

# reset to commit hash
git reset --hard <hash>

# commit changes from staging area
git commit -m "Message to commit with"

# commit something into the last (HEAD) commit
git commit --amend -m "New commit message"
# or without new -m "message"
git commit --amend --no-edit
# used for something you forgot to add and what should be in that same commit
# used BEFORE you push

# push local commit to master branch of origin repo 
# and link it to `upstream` with -u (short for --set-upstream)
git push -u origin master

# same for branch (not master/main)
git push -u origin feature/merge-request

# after linked with -u, can just 
git push

# delete remote branch
git push origin --delete feature/merge-request

# pull all commits from upstream to current branch
git pull

# diff between commits
# can also be used agains branches
git diff A B

# diff between commit and staged
git diff --staged A B

# create new branch from current
git branch newBranch

# git checkout == git switch
# create new branch from current and switch to it
git checkout -b newBranch
git switch -c newBranch

# show branches
git branch

# show all branches, inc remote
git branch -a

# remove local branch
git branch -d newBranch

# remove local branch forced 
git branch -D newBranch

# merge newBranch to current
git merge newBranch 

######
# basic workflow looks like 

#> fork on GitHub

git clone <your fork>
git checkout -b my-task-branch-name

#> here goes your work

# before push refresh main from GitHub (not for a personal fork)
git checkout main && git pull 
# merge my task to fresh main
git checkout my-task-branch-name && git merge main

git push -u origin my-task-branch-name
-> fix merge conflict
git commit -m 'merge main'
git push
######
```
