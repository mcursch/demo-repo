# Git commands and their meaning 
## Git Add
Git add adds a file to the tracking of git. if a file is not added, it will not be staged for a commit
git add takes modified file in working directory and places modified version in staging area

Git add is a multipurpose command: it tracks new files, stages files, and marks merge-conflicted files as resolved.

Can also be thought of as "add this content to the next commit" instead of "add files to project" because you use git add on files that have already been git added

## Git [-a] [-m] commit
commit records the snapshot you set up in your staging area

adding -a will skip the staging area requirement, essentially adding and committing at the same time

## Git rm [-f] <filename>
Git rm will need to be removed from staging area and then committed
git rm does that and removes the file from your working directory so you dont see it as untracked

## Git Push
Pushes your changes to remote repository


## git reset
undoes a git add 

## git reset HEAD~n
sets HEAD to point n commits backwards. Doing n=1 will set back 1 commit, effectively undoing 1 commit

## git reset <hash>
put the has of a git logged ommit in here in order to go back to that commit

## git reset <hash> --hard
completely go back and get rid of all changes instead of just unstaging them

## git status
shows the current status, what files are tracked/need to be committed

## git diff <branch>
shows the difference in branches between the current branch and the specified branch
git diff by itself will show unstaged changes in your current branch, basically the difference between the branch and itself

## git log
gives log of commits in reverse chrono order. shows hashes which can be used to specify which branch

## git merge <branch>
merges branch into the branch called on. So, calling this while on master branch would merge branch into master

# Forking in Git 
if you dont have access to a repo, you can fork the repo, which will basically copy the repo and allow you to make changes

# Merge Commit
one way of merging code, via git merge brannch --squash
will cause code to be merged into one glob and put on top of branch calling merge, which will then be committed and have that name

EX: m1->m2->m3                  m1->m2->m3->mc1
        |               ...         
        f1->f2
when running a merge commit, , called say, mc1, will result in a log of ^^

But what if we want to see f1 and f2 commits?

## git rebase <branch>

called from a branch, looks at branch, finds commit both branches have in common, saves changes that calling branch has, then adds changes from common point on <branch>, adds them on top of calling branch, then adds saved changes from calling branch on top of that

EX: m1->m2->m3                
        |                       
        f1

calling rebase from f1 via git rebase master turns feature branch, which would normally be logged as 
m1->m2->f1 into m1->m2->m3->f1
m2 is common branch, saves f1, adds branch m3 changes, then adds saved f1 changes

Now, do f2, so feature branch is now

m1->m2->m3->f1->f2

go to main, call rebase again
finds common point of both, m3, saves changes, which is none here, then goes to feature and adds changes to master, f1->f2 here, then adds master changes (none)

now master is m1->m2->m3->f1->f2

## Tracked vs Untracked Files
tracked files are files in the last snapshot, as well as any newly staged files. They can be unmodified, modified, or staged
Tracked files are files Git knows about

Untracked files are everything esle. all files not in last snapshot and not in your staging area.

Adding a new file will show as an untracked file, which makes sense since git has no knowledge of that file


new new stuff