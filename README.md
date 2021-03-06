# git-workflow

# Just resolving a simple merge conflict

Assume that changes have been made by other users to the development branch (the changes are on the second line of each file) we have to make changes locally on the second line of each file so we can create a conflict. Also in one of the files i will make a change to the very last row

I then commit of my local changes

### Note better to use git add -A instead of git add .

then 

### git commit -m "commit message"

then i want to fetch all the changes. It is better if i dont use pull cause the merge process will start automatically.

### git fetch --all

If i want to abort a merge conflict i just have to write

### git merge --abort

Now if i type

### git status

i will see that there is a message that the branches have been diverged

Now that i am ready to to merge i write

### git merge origin/development

i will get a notification that i have a merge on the files that i have a conflict.

if i type git status i will see the files that have a conflict it will say that both modified next to them. This means that these files have been modified both locally and on the remote branch

### git status

i have to start opening each file that has a conflict and then resolve it. i can either use vim or VSCODE

anything between <<<<<<< HEAD and the =============== is your local changes anything below =============== are the changes on the remote branch. In order to resolve the conflict we have to delete any part of the we dont need (we can either keep our changes or the remote changes or a combination of both. What we should always do is that we have to remove the <<<<<<< HEAD adn ============)

once we are done with the file we just have to press esc :wq to exit vim

Note: to copy on vim you can use shfit + drag mouse over the text then press ctr +shift + c and then noremal ctr v to paste in another place outside vim

the next step is to add this file

#### git add name_of_file

now we can use

### git status

again to see what are the remainig files that have a conflict which we need to resolve

TIP: if you have many conflicts in 1 file and you need to find them you can use the search functionality in vim

you need to type esc /<<<<<<< HEAD then press enter
with the n you go to the next instance with N you go to the previous instance. If you wnat to exit search you just have to press esc

Extra vim tip in the normal mode gg gets you to the top of the page (better place to start your search) G takes you to the end of the page

if a folder is on a subfolder we have to either navigate there with the terminal and add it with git add name_of_file or in the root of our project to type /folder/file

### git status

once again to see if there are extra file we need to resolve

if we dont see any file with both modified on git status it means that we have solved all the issues

2 extra ways to make sure that there are no extra conflicts

### git diff --name-only --diff-filter=U

or

### grep -H -r "<<<<<<< HEAD" .

once we are 100% sure that there are no extra conflicts we can just use the

## git commit -m "fixing the conflicts"

Once you are sure that you are not any conflict between the branch you are working on and the remote branch it is also a good practice to make sure that there are no conflcits between your branch and the master before subiting a pull reuqest

if i want to see visually how the git workflow looks like

### git log --oneline --decorate --graph --all

Now that i have pushed all my changes to the branch that i am working on and i am about to do a pull request on the master it is better to make sure that i dont have any conflcits with the master before starting the pull request. Lets say that someone has made changes to the master that i dont have locally

i will do a

### git fetch -- all

then

### git merge origin/master

### git status

to see the files that have the conflcit and start resolving the conflicts 1 by 1 in each file after fixing the conflicts to each file
i will stage the file with

git add name_of_file

once i am done i have to do a commite

### git commit -m "commit message"

then i am readly to push my changes to development branch and open a pull request to the master

## Squash commits

## Git rebase
