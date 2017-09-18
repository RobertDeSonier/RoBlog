---
layout: post
title: Run Git prepare-commit-msg Hook on Previous Commits
date: 2017-08-24 07:00:00
categories: git scripts
---

I've had some people approach me after adding a git hook I made saying, now that I have the hook in place, how do I fix all my previous commits to use it?!

Once again, I offer some good news! It is possible and easy to run the git hook on your previous commits using [Interactive Rebase](https://git-scm.com/docs/git-rebase#_interactive_mode).

Here is how you fix up all your previous commits to run the pre-commit hook you just added:
1. Select commit prior to commits you want to run the hook on.
1. Right-click > Rebase current branch on > Select Commit Hash  
![Rebase Right-click]({{ site.url }}/assets/2017-08-24/Rebase.PNG)
1. Click Show options
1. Check Interactive Rebase
![Interactive Rebase Check]({{ site.url }}/assets/2017-08-24/InteractiveRebase.PNG)
1. Press Rebase
1. Your choosen Text Editor should open with git-rebase-todo window
![Rebase Todo]({{ site.url }}/assets/2017-08-24/RebaseTodo.PNG)
1. Add `exec git commit --amend -C HEAD` after each commit
![Rebase Todo Edited]({{ site.url }}/assets/2017-08-24/RebaseTodoEdited.PNG)
1. Close the edit window
1. Watch git do it's work!