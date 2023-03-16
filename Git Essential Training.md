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

#add a file .gitkeep to keep track of an empty folder
git restore --stagged "filename"

git restore . #to undo changes

git log --oneline

git revert "checksum or commit id"

```