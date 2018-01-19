---
layout: post
title: Interactive Rebase with Pancakes!
date: 2018-01-22 07:00:00
categories: git
---

In a [previous post]({{ site.baseurl }}{% post_url 2017-10-12-Rebasing with Pancakes %}), we talked about the basics of rebasing by moving a stack of pancakes.

This is my second post in the Rebasing with Pancakes. This post will cover an overview of the interactive rebase.

I want to remind you before you move on, as you try out interactive rebase, rely heavily on [The Magic of Reflog]({{ site.baseurl }}{% post_url 2017-11-16-The Magic of Reflog %}) to help you learn with confidence.

## What can Interactive Rebase do?

Interactive rebase can do so much more than move commits from one branch to another, so were gonna need more stacks of pancakes to begin to uncover everything it can do for us.

When you first begin your interactive rebase, you will be presented with these options (which you can mix and match to your heart's desire):  
[pick](#pick)  
[drop](#drop)  
[reword](#reword)  
[edit](#edit)  
[squash](#squash)  
[fixup](#fixup)  
[exec](#exec)

These options are what makes interactive rebase so much more than a basic rebase, so it's important to understand each one:

### pick:

Pick will allow you to change the order of your pancakes, but after everything you will still have the same pancakes you started with.

![Pancakes => Pancakes]({{ site.baseurl }}/assets/2018-01-22/pickPancakes.JPG)

Pick says, I want this commit here just as it is.

### drop:

Drop is how you eat one of your pancakes, so it no longer exists in your stack.

![3 Pancakes => 2 Pancakes]({{ site.baseurl }}/assets/2018-01-22/dropPancakes.JPG)

Drop is used to remove a commit.

### reword:

Reword is how you order pancakes in Greek, you still have pancakes, they are just called something different.

![Pancakes => Τηγανίτα]({{ site.baseurl }}/assets/2018-01-22/rewordPancakes.JPG)

Reword allows you to change the commit message (in the language of your choice).

### edit:

Edit is the alchemy of pancakes. We can do just about anything to our pancakes with the edit option.

We can remove part of our pancakes.
![3 Pancakes => 2.5 Pancakes]({{ site.baseurl }}/assets/2018-01-22/edit1Pancakes.JPG)

We can add chocolate chips to one of our pancakes (all metaphors eventually fall short).
![3 Pancakes => 3 Pancakes w/ chocolate chips]({{ site.baseurl }}/assets/2018-01-22/edit2Pancakes.JPG)

We can change one of our pancakes into a waffle.
![3 Pancakes => 2 Pancakes, 1 Waffle]({{ site.baseurl }}/assets/2018-01-22/edit3Pancakes.JPG)

Edit, in the simplest definition, allows you to remove from, add to, and completely change your commit.  
This is one of the harder and most useful options at your disposal, so take the time necessary to learn this one.

### fixup:

Fixup is how you make your 3 pancakes into 1 big pancake (My 3 year old daughter loves this one).

![3 Pancakes => 1 Big Pancake]({{ site.baseurl }}/assets/2018-01-22/fixupPancakes.JPG)

Fixup lets you combine a bunch of commits into a single commit.
This is nice if you are using frequent small commits, it allows you to bring those commits together into a clearer single commit (Your code review buddy will love this one).

### squash:

Squash lets you order your 1 big pancake in Greek.

![3 Pancakes => 1 Big Τηγανίτα]({{ site.baseurl }}/assets/2018-01-22/squashPancakes.JPG)

Squash is a combination of Fixup and Reword, so you combine a bunch of commits and then change the commit message.

### exec:

Exec tells your butter robot to butter each pancake as they are stacked.

![3 Pancakes => Robot butters each pancake as they are stacked]({{ site.baseurl }}/assets/2018-01-22/execPancakes.JPG)

Exec lets you run a command in the middle of your rebase.  
This option is less common, but when needed very helpful.
The only time I have really used it, was to run a script that modifies each commit message after they were committed.

## How to Interactive Rebase:

### In command line:

 1. Checkout your branch (if not already checkout out) by running: `git checkout your-branch`
 1. Then run: `git rebase -i other-branch`
 1. A text editor should pop-up with something similar to this:
 ![CLI - Initial Rebase Window]({{ site.baseurl }}/assets/2018-01-22/CLIRebase1.PNG)
  - You can see, all of the options available are listed in the commented out section at the bottom.
 1. Set the options for each commit you want to change, eg:
 ![CLI - Options Set Rebase Window]({{ site.baseurl }}/assets/2018-01-22/CLIRebase2.PNG)
 1. Save, Close, and watch git work.

### In GitExtensions:

 1. Checkout your branch
 1. Right-click the branch you want to rebase on.
 1. Select `Rebase current branch on` and then select the branch you want to rebase on.
 ![GE - Rebase Menu]({{ site.baseurl }}/assets/2018-01-22/GERebase1.PNG)
 1. Once you get the window below, select `Show options`:
 ![GE - Rebase Show Options]({{ site.baseurl }}/assets/2018-01-22/GERebase2.PNG)
 1. Then check `Interactive Rebase` and press Rebase:
 ![GE - Rebase Show Options]({{ site.baseurl }}/assets/2018-01-22/GERebase3.PNG)
 1. You will be presented with the same window as with Rebasing in the command line:
 ![CLI - Initial Rebase Window]({{ site.baseurl }}/assets/2018-01-22/CLIRebase1.PNG)
  - You can see, all of the options available are listed in the commented out section at the bottom.
 1. Set the options for each commit you want to change, eg:
 ![CLI - Options Set Rebase Window]({{ site.baseurl }}/assets/2018-01-22/CLIRebase2.PNG)
 1. Save, Close, and watch git work.

Any conflicts will appear as git rebases your branch, so you can solve them on the commit where the conflict occurs.

## Lessons Learned:

 - Interactive Rebase becomes significantly more useful the smaller the changes your commits contain (it is always easier to combine commits rather than split them apart).
 - If you have to rebase a branch pushed to the server (eg. GitHub), be sure to notify anyone who could be using that branch as well.


