# Git

Remove all local branches except master:

    git branch | grep -v "master" | xargs git branch -D
