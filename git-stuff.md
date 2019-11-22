# git stuff
## 1 github
   - create a repository online
    - public or private
    - gitignore: does not save this files/dirs
    - licenses
##2 Commits
 - 'Saves the current version
 - important for version control
 - please write always a brief description what are the changes about
 - does direcly appear under the commit hash
        -what is changes in this version
- in hash files the changes between different commits are stored

##3 branches
- master branch
- copy of a certain commit (version) changes on different branches are possible
- parallel version of software are possible starting from one commit
- branches can be merged back together
- git shows conflicts between commits and asks which changes in the different commits should be kept
- git merge ours/theirs


##4 clone
git clone  NAMEofREPO 
- go to where you want to have the repository in
- git clone https://github.com/Plant3000/swc-stuttgart-221119.git


##5 .git
Directory with all the stuff containing git, whereas .gitignore is extra

##6 changes in the local repository
New data was created in the local repository
###6.1 git functions
- git init
- git add
- git push
- git commit


###6.2 git functions correct order
1. git add 
    - git add --all: all data in will be added to the commit
    - git add FILENAME better to add just the files you changed

2. git commit -m 
      - creates a new checkpoint/version
      - first time, asked about user
        - git config --global user.email patrick_patrick@web.de   
        - git config --local user.email patrick_patrick@web.de     (local user for this repo)
        - git config --local user.name Plant3000 (local user for this repo)
       - git config --local user.password"**": saves PW
       - git config --local credential.helper store
       -> speichert passwort unser userdaten, eingabe immer muss nicht gemacht werden 
   - git config --local user.signingkey -> anstelle von user.password


Fehler PW speichern
Speichern des PW hat nicht so recht geklappt. Nochmal nachschauen wie man das macht
 - git config --global credential.helper 'cache --timeout=3600'   (should work from: https://help.github.com/en/github/using-git/caching-your-github-password-in-git )

   - git config --list (for c
       - git commit -m "TEXT" ->  creates the 

3. git push
 - pushes the new changes in the commit to the master
 - config

4. git status
    -  what is going on, up to date?
    - Changes not staged for commit:
    - git add is not done 
    -after git add, local tree is updated, server repo not changed -> git push
    - color red: file modified but not commited
    - color green: file modified and commited 

5. git fetch 
    - checks if the server version is changed.
    - to see if up to date git log and see if commit hash is the same

6. git diff
    - compares files
    - git diff --staged
    - git diff HEAD FILENAME: shows what changed in the file
    - git diff HEAD~NUMBER FILENAME: shows what changed in the file in comparison to NUMNBER of commits back

7. git log
    - shows the versions
    - git log --oneline
    - git log -2 --oneline : last two commits


###6.3 Contribute to other repos
1. If on github: first got to own repositiory 
2. Settings, enter PW, and add  collaborator so others can add your repository. If you want to edit other repos, the other owner has to do that
3. Now a push should be work


###6.4 all git add, commit and push
 - git add --all && git commit -m "commit on "$(date +%d/%m/%Y)" at "$(date +%H:%M:%S)"" && git push origin master

- git add --all && git commit -m "commit on "$(date +%d/%m/%Y)" at "$(date +%H:%M:%S)"" && git push origin BRANCHNAMES      -> (which to push from)

###6.6 git revert
 - git checkout HEAD~NUMBER FILENAME -> changes the FILENAME to NUMBER of versions back from HEAD

###6.7 branching
 - git branch -> lists branches , it can list, create and delete branches
 - git checkout -> to some extent switches branches and restore working tree files
 - git checkout -b -> creates a branch and moves HEAD to branch
 - git branch gh-pages ->github webpage (on github one webpage for free)
 - git branch ->to check on which branch. '*' indicates on which branch
 - git checkout BRANCHNAME -> switches to branch 
 - git checkout -b  NAME -> creates new branch
 - git push --set-upstream origin gh-pages
    -> pushes local gh-pages to server gh-pages

####6.7-1 . Merge local branch to another:
 First, checkout to your Branch3:

 -git checkout Branch3

- Then merge the Branch1:

- git merge Branch1

- And if you want the updated commits of Branch1 on Branch2, you are probaly looking for git rebase

- git checkout Branch2
- git rebase Branch1



















