# Git

* New added files are "untracked files"
* Changed files are "modified files"

To add changes of files and new files:
```bash
$ git add -A
```

To see status:
```bash
$ git status
```

To see the logs:
```bash
$ git log
```

To commit with a message:
```bash
$ git commit -m <description message>
```

To see the differences where HEAD is (latest commit by default):
```bash
$ git diff HEAD
```

To see the differences in the staged:
```bash
$ git diff --staged
```

To unstage something:
```bash
$ git reset <file names>
```

To revert changes to the latest commit in a file (must be unstaged first):
```bash
$ git checkout -- <filename>
```

To list the branches:
```bash
$ git branch
```

To create a new branch:
```bash
$ git branch <name of branch>
```

To change to a branch:
```bash
$ git checkout <branch name>
```

To merge <branch name> with <master> (be in master and execute this):
```bash
$ git merge <branch name>
```

To delete a file both from git and filesystem:
```bash
$ git rm <file name>
```

To delete a branch:
```bash
$ git branch -d <branch name>
```

To clone:
```bash
$ git clone <url>
```

To push (-u is to eliminate the need of entering "origin master" every time):
```bash
$ git push -u origin master
```

To pull:
```bash
$ git pull
```

To list remotes:
```bash
$ git remote
```

To list remotes (verbosly):
```bash
$ git remote -v
```

To add remote:
```bash
$ git remote add origin <url>
```

Notes:
1. use separate commits for separate tasks
1. use branches to tidy things up (or when you work in a group)
1. when two lines of a same file are changed simultaneously on different hosts
(like remote and local) then a conflict happens. To resolve it, we can pull
the remote and edit the conflict file. There would be a <<<<<<< HEAD which
indicates the local changes in our HEAD untill the ======= line. And then the
remote will come after that with >>>>>>> <has of remote commit>. Edit the
file to what it should be and then delete all those <<< HEAD and >>> HASH.
Then add and commit the files and only then you will be able to push to the
remote repository.
