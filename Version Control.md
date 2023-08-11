Git for Version Control, Collaborations and Managing Open Source

```bash
git init
git add .
git commit -m "initial commit"
git remote add origin "repo url"
git push --set-upstream origin main

new-item -name 'name of file with extension' #will be added to repo

git status
git push origin main
git pull 

git diff
git diff --cached

git log
git show "checksum"
git log -p

git log --graph
git log --oneline

git restore --stage "filename" #to unstage a file


#add a file .gitkeep to keep track of an empty folder
git restore --stagged "filename"

git restore . #to undo changes


git revert "checksum or commit id"

```

## Git Commit Messages
* What Changes were applied
* Use Present Tense
* First line Should be max 50 Characters 
If your message is long don't pass any argument in command just type git commit it'll ask for message in a code editor there you can type long messages.

```bash
ssh-keygen -t ed25519 -C "your@email.com"
```

## Types of Version Control Systems

- Subversion
- Perforce
- AWS Code Commit
- Mercurial
- Git

Two main types:

- Centralized Version Control System
- Distributed Version Control System

## Git Workflow 

It contains total 3 states
- Modified
- Staged
- Committed

## Centralized Version Control 

It consists of a server and a clients. The clients need to pull codebase from the server in order to work on it. each client has its own copy of the codebase. Server is the central copy of the project. In order to retrieve and view the changes and change history we need to be connected to the server.
- Easier to Learn
- More access control to the users
- Slower

## Distributed Version Control

It is similar to the CVCs but we still need to pull the code from the codebase to view the latest changes. The key difference is that every user is a server not a client. It means once we pull from the distributed model we will have the whole change history on our system.
- No connection to the server required
- Better speed and performance

Many companies setup different environments for during the development such as staging and QA environment. The staging environment mimics the production environment. This allows us to test new features prior to the release. Staging area also help us in migrations.

It is recommended to perform a git pull before doing a push request.