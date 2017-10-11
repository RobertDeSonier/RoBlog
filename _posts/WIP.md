---
layout: post
title: Git Rebase
date: 2017-10-10 07:00:00
categories: Git
---

I have had a lot of people approach me with questions that could be solved with a [Git Rebase](https://git-scm.com/book/en/v2/Git-Branching-Rebasing), so I wanted to write a couple posts about it.
There are two methods of rebasing, the basic rebase and the interactive rebase.
These two methods are so different for when it comes to use them and what they are used for, I wanted to create separate posts for each.

This post will be focused on the basic rebase.

## What is Rebasing:

I feel like an illustration could help with this, so lets say you and a friend have a stacks of pancakes each.
Your friend's stack has 5 pancakes and your stack only has 1! Clearly we need to fix this.
To fix it, you move the top 2 pancakes from your friend's stack to your stack.
![pancakes]({{ site.baseurl }}/assets/WIP/pancake.PNG)

That is the basic rebase.
You move commits from one branch to another.

## When to Rebase:

As with the pancakes, sometime you want your branch to be based on another branch:
![MoveBranch]({{ site.baseurl }}/assets/WIP/moveBranch.PNG)

Most of the time though, the basic rebase is best used to replace a merge so your branch is up to date with the base branch:
![RebaseOnTop]({{ site.baseurl }}/assets/WIP/rebaseOnTop.PNG)
By Rebasing your branch on top, instead of merging, you get a cleaner history without a bunch of merge commits updating your branch.

## How to Rebase:

