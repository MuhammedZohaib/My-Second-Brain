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

git diff
git diff --cached

git log
git show "checksum"
git log -p

git log --graph
git log --oneline


#add a file .gitkeep to keep track of an empty folder
git restore --stagged "filename"

git restore . #to undo changes


git revert "checksum or commit id"

```

## Git Commit Messages
* What Changes were applied
* Use Present Tense
* First line Should be max 50 Characters 
If your message is long don't pass any argument in command just type git commit it'll ask for message in a code editior there you can type long messages.

