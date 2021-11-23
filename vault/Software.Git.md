---
id: DnfP7up0cIhvaUWp23Jtk
title: Gir Workshop and Notes
desc: ''
updated: 1637709642418
created: 1636428241249
---

https://monashdatafluency.github.io/git-tutorial/

## Notes

```
git add
git commit -m
git commit -am
git status
git log
git checkout
git switch

# danger !
git merge
git rebase

git reset
```

## Installation and Setup

Configuring git for first time use is very tedious and annoying.

```
git config --global user.name "Name"
git config --global user.email "email"
```

Configure a text editor for git with the following (replace the quotations with the text editor command)

More options are available here:
https://www.atlassian.com/git/tutorials/setting-up-a-repository/git-config

Note that by default git uses vim, which has a steep learning curve.

```
git config 00global core.editor "atom --wait"
```

The following command lets you see a rudimentary graphic of your history (investigate later)

```
git config --global alias.lsd "log --graph --decorate --pretty=oneline --abbrev-commit --all"
```

Then you can use 

```
git lsd
```

to visualise.

### SSH keys

To alleviate the headache of logging in everytime, Git uses SSH keys.
```
ssh-keygen -t rsa -b 4096 -C "Your.Name@email.com"
```

```
eval "$(ssh-agent -s)"
ssh-add -K ~/.ssh/id_rsa
```

Copy the contents of the .pub file, and paste this into GitHub settings to configure it.

Test the connection via an ssh command

```
ssh -T git@github.com
```

## Git Theory 

origin refers to the original GitHub hosted link. 

On the origin, this has the master branch.

On the LOCAL machine, you also have a master branch.

Hence, when your local machine's master branch is up to date, this is good!

Use 

```
git add <file>
```

And track changes with 

```
git status
```

Note on style. Make comments all in present imeprative tense. E.g.

"Fix bug Z", "Document function Z", etc.

Remove additions with 

```
git reset
```

### Branches

For big changes, it is better to use new branches so that changes are isolated from the main branch.

In practice, this is always preferable - learn how to do this!

The below code switches to a branch, create a new one, with the name use-packing

```
git switch --create use-unpacking
```

The -am flag is short for commiting all changes, to files that already exist. If these files do not exist, they need to be added first with git add.

Note that `git add .` and `git add --all` (`git add -A`) are identical!

```
git commit -am ""
```

After commiting changes to the branch, switch back to the main branch. Then merge the two branches together.

```
git switch 
git merge use-unpacking
```

Git is usually smart enough to automatically merge differences without any issues. 

However, sometimes it cannot do this automatically.

After any git status, you can "revert" back to an earlier version by using the git checkout command.

checkout automatically switches you to a temporary branch. 

You can save any changes in this temporary branch by saving it as a new branch. git switch -c <branch name>

Or, you can discard changes by running git switch -

Note that all commit history IS properly reflected in the final GitHub repo. 

Note that branches which have not yet been merged will be reflected online.

However, if all branches have been merged, there are no remaining branches, and the main GitHub site will reflect this.

#### Git is a mess

The below all do (more or less) the same thing. 

This is because git checkout is too overloaded and has too much functionality. So, switch was created to lighten its workload. It is a newer command, so this is why some people do not use it.

For the most part, checkout and switch do the same thing.

Note that switch is created ONLY for switching to the HEAD (latest) version of any branch. 

checkout lets you, by design, checkout ANY pervious version of any branch, as opposed to JUST the latest (HEAD).

```
git switch -c "new-branch"
git checkout -c "new-branch"
# git branch does not automatically switch
git branch -c "new-branch"
```

git reflog is the closest to an undo button.

### Merging Conflicts

It is recommend to use VScode for this. VScode offers a very nice built in UI for handling merges etc.



## Advanced Topics

This tutorial did not go through git rebase.

Apparently rebase and merge were both created to solve the same problem, but do so in different ways.

It seems that either is controversial, like tabs vs spaces sort of thing.

Majority of people seem to just use merge.


