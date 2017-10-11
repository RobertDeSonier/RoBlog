---
layout: post
title: Git Rebase
date: 2017-10-10 07:00:00
categories: Git
---

I have had a lot of people approach me with questions that could be solved with a [Git Rebase](https://git-scm.com/book/en/v2/Git-Branching-Rebasing), so I wanted to write a couple posts about it.
There are two methods of rebasing, the basic rebase and the interactive rebase.
These two methods are so different for when to use them and what they do, I wanted to create separate posts for each.
This post will be focused on the basic rebase.

## What is Rebasing:

I feel like an illustration could help with this, so lets say you and a friend have a stacks of pancakes each.
Your friend's stack has 5 pancakes and your stack only has 1! Clearly we need to fix this.
To fix it, you move the top 2 pancakes from your friend's stack to your stack.
![pancakes]({{ site.baseurl }}/assets/WIP/pancake.PNG)

That is the basic rebase.
You move commits from one branch to another.

## When to Rebase:

Sometimes it is because there really is a new branch someone made that you want your commits to be on top of.
Most of the time I see the need for a basic rebase, is the branch you originally started working off of has changed and you need changes from that branch to either merge a pull request or to get new features it has.
```
Side note:
This could be solved with a merge as well, but a rebase would allow your branch's history to not be muddled with merge commits.
```

## How to Rebase: