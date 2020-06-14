# Git Stuffes

A place to practice git commands so that I can keep my git skills sharp.


# Resources

## Git Basics

YouTube tutorials that I have found useful:
* [Introduction to Git: Core Concepts](https://www.youtube.com/watch?v=uR6G2v_WsRA)
* [Introduction to Git: Branching and Merging](https://www.youtube.com/watch?v=FyAAIHHClqI)
* [Introduction to Git: Remotes](https://www.youtube.com/watch?v=Gg4bLk8cGNo)

Note: The creator of the above three tutorials has yet to create the fourth in the series about rebasing and cherry picking.



## Rebasing
YouTube tutorials that I have found useful:
* [A better Git workflow with rebase](https://www.youtube.com/watch?v=f1wnYdLEpgI)

Websites/Articles:
* [A better Git workflow with rebase (supporting article)](https://www.themoderncoder.com/a-better-git-workflow-with-rebase/)
* [The Golden Rule of Rebasing](https://www.atlassian.com/git/tutorials/merging-vs-rebasing#the-golden-rule-of-rebasing)
 
Note: Here be dragons. Most opinions point towards rebasing master as being a very bad thing. Rebasing feature branch on master less of a bad thing, but care still needed. Seems most people use it to keep the merge commits out of master, thus keeping the commit log cleaner. The comments in the video also point to a way to do a different kind of merge that seems to do a squash of the feature commits. Some more research into the pros and cons of rebasing required.

## Rewrite history
Youtube tutorials that I have found useful:
* [Rewriting Git history - Amend reword, delete, reorder, squash and split](https://www.youtube.com/watch?v=ElRzTuYln0M)
* [Git Tutorial: Fixing Common Mistakes and Undoing Bad Commits](https://www.youtube.com/watch?v=FdZecVxzJbk)

Websites/Articles:
* [Techniques for rewriting Git history](https://www.themoderncoder.com/rewriting-git-history/)

## Git utilities
### Bash prompt
You can display the current git branch on the bash prompt using `.git-prompt.sh`. Further details [here](https://web.archive.org/web/20160704140739/http://ithaca.arpinum.org/2013/01/02/git-prompt.html) and [here](https://stackoverflow.com/questions/15883416/adding-git-branch-on-the-bash-command-prompt)

The shell script can be found [here](https://github.com/git/git/blob/master/contrib/completion/git-prompt.sh)
My current bash prompt is configured like this:
```bash
...
# source the git prompt script so that we can display the branch
# name in the prompt.
source ~/.git-prompt.sh

GIT_PS1_SHOWDIRTYSTATE=1
GIT_PS1_SHOWSTASHSTATE=1
GIT_PS1_SHOWUNTRACKEDFILES=1
GIT_PS1_SHOWCOLORHINTS=1
GIT_PS1_DESCRIBE_STYLE="branch"
GIT_PS1_SHOWUPSTREAM="auto git"
...
if [ "$color_prompt" = yes ]; then
    PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\[\033[01;33m\]$(__git_ps1 " [%s] ")\[\033[00m\]$ '
else
    PS1='${debian_chroot:+($debian_chroot)}\u@\h:\w\$[__git_ps1]\$ '
fi
...

```

### Git auto completion
You can enable git autocompletion for things like branch names by sourcing the `git-completion.bash` script in `.bashrc`.

The shell script can be found [here](https://github.com/git/git/blob/master/contrib/completion/git-completion.bash)
