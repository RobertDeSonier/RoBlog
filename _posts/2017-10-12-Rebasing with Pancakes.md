---
layout: post
title: Rebasing with Pancakes!
date: 2017-10-12 07:00:00
categories: git
---

I have had a lot of people approach me recently with questions that could be solved with a [Git Rebase](https://git-scm.com/book/en/v2/Git-Branching-Rebasing), so I wanted to write a couple posts about it.

There are two methods of rebasing, the basic rebase and the interactive rebase.
These two methods are so different for when it comes to use them and what they are used for, I wanted to create separate posts for each.

This post will be focused on the basic rebase.

## What is Rebasing:

I think an illustration could help with this, so lets say you and a friend have a stacks of pancakes each.

Your friend's stack has 5 pancakes and your stack only has 1! Clearly, we need to fix this.

To fix it, you move the top 2 pancakes from your friend's stack to your stack.
![pancakes]({{ site.baseurl }}/assets/2017-10-12/pancake.PNG)

That is the basic rebase.
You move commits from one branch to another.

## When to Rebase:

As with the pancakes, sometime you want your branch to be based on another branch:
![MoveBranch]({{ site.baseurl }}/assets/2017-10-12/moveBranch.PNG)

Most of the time though, the basic rebase is best used to replace a merge so your branch is up to date with the base branch:
![RebaseOnTop]({{ site.baseurl }}/assets/2017-10-12/rebaseOnTop.PNG)
By rebasing your branch on top, instead of merging, you get a cleaner history without a bunch of merge commits updating your branch.

## How to Rebase:

### In command line:

 1. Checkout your branch (if not already checkout out) and run: `git checkout your-branch`
 1. Then run: `git rebase other-branch`

The rebase command accepts a wide range of arguments (eg. you can rebase using a hash with `git rebase ba3217...`).
Go checkout out the [documentation](https://git-scm.com/book/en/v2/Git-Branching-Rebasing) if you want to know more about advanced rebasing.

### In GitExtensions:

 1. Checkout your branch
 1. Right-click the branch you want to rebase on.
 1. Select `Rebase current branch on` and then select the branch you want to rebase on
 ![GitExRebase]({{ site.baseurl }}/assets/2017-10-12/gitExRebase.PNG)
 1. Once you get the window below, select Rebase:
 ![GetExRebaseForm]({{ site.baseurl }}/assets/2017-10-12/gitExRebaseForm.PNG)
 1. Then sit back and watch it work.

Any conflicts will appear as git rebases your branch, so you can solve them on the commit where the conflict occurs.

## PS:

There will still be cases where a merge is better than a rebase (eg. There are so many conflicts, it would be easier to solve them all in one merge commit).

I believe a good rule of thumb is, rebase first and use merge as a back up for when the rebase gets too much to handle.