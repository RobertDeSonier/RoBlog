---
layout: post
title: The Magic of Reflog
date: 2017-11-16 07:00:00
categories: git
---

After my [last post]({{ site.baseurl }}{% post_url 2017-10-12-Rebasing with Pancakes %}) on rebasing, I have received a lot of comments from fellow Developers expressing their concern for messing up their branch with a rebase.

And I understand that re-writting history is scary.

So, before we move onto interactive rebase, I want to introduce you to [git reflog](https://git-scm.com/docs/git-reflog).  
These 10 characters have saved me from massive mistakes, countless times.  
This command is the reason I ever use rebase, let alone suggest others do it too.

With the knowledge of git reflog, you can go forward with learning and practicing rebasing without the fear of destroying history or losing code.

## What is this mystical git reflog?

Git reflog is simply a log of everything you have done in git.  
It is history of the actions you have performed in git for the past 90 days (by default).

## Does sounds very magical, does it at least look magical?

Maybe a little bit... but not really.  
![reflog1]({{ site.baseurl }}/assets/2017-11-16/reflog1.PNG)

## So, what does this mean?

This means, you can undo almost anything.  
For example, in my reflog I have a `BAD COMMIT` at `HEAD@{0}`:  
![reflog2]({{ site.baseurl }}/assets/2017-11-16/reflog2.PNG)
If I run the command `git reset HEAD@{1}` (the address before the BAD COMMIT), it will reset my repo to before the commit happened.  
So, I now have the ability to fix that BAD COMMIT.

Even more good news, if I run `git reflog` again:
![reflog3]({{ site.baseurl }}/assets/2017-11-16/reflog3.PNG)
You can see, even the reset command I used can be undone.  
It really does keep track of almost everything you do!

## Hmm, what does this have to do with rebasing?

For my next post, I want to talk about the interactive rebase.  
With interactive rebase, the power and beauty of git begins to reveal itself, but it also has a learning curve to it that will cause you to make mistakes and get dirty.  

The good news is, those mistakes can be undone and you can try to rebase again with more knowledge and experience now that you know `git reflog`.

So you see, the magic of `git reflog` is not what it does, but what it provides.  
It gives you the confidence to go forward playing with and learning git.

## PS:

This is a log of your local changes, so if you push to the server (eg. GitHub) that cannot be undone using `git reflog`.  
So, if you are practicing something new or complicated, just do it locally, then push once you have it correct locally.

## PSS:

A good rule of thumb with Git, if the word `force` is involved in what you are doing, proceed with caution.  
Most `force` commands cannot be undone, you will lose something if you use `force` incorrectly.