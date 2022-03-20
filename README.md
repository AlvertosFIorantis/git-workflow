# git-workflow

# Just resolving a simple merge conflict

Assume that changes have been made by other users to the development branch (the changes are on the second line of each file) we have to make changes locally on the second line of each file so we can create a conflict. Also in one of the files i will make a change to the very last row

I then commit of my local changes

Note better to use git add -A instead of git add .

then i want to fetch all the changes. It is better if i dont use pull cause the merge process will start automatically.

### git fetch --all

If i want to abort a merge conflict i just have to write

### git merge --abort

Now if i type

### git status

i will see that there is a message that the branches have been diverged
