---
layout: post
title: Sublime - Tip 0 - Setting up a Project
date: 2017-09-14 07:00:00
categories: sublime
---

As the Pragmatic Programmer says `"Tip 22: Use a Single Editor Well"`.  
I chose [Sublime](http://www.sublimetext.com/) as that editor, because it is configurable, extensible, and programmable.  
Sublime is my go to editor for a majority of my text editing (from development to writing emails).  
That being said, I wanted to create some blog posts with tips that helped me to make Sublime my end all editor.  
And since all good lists start with index 0, here is tip #0:

## Setting up a Project:

If you will be editing code in a project with Sublime, the first thing you need to do is set-up a project.  
Luckily, this is a very simple thing to do in Sublime that will make editing code in a project much easier.

 1. `Ctrl + Shift + P` (this opens the Sublime Command Pallet, this is where you can get to anything in Sublime)
 1. Type and Select `Project: Add Folder`
 1. Navigate to the folder containing the project you wish to add.
 1. `Ctrl + Shift + P`
 1. Type and Select `Project: Save As`
 1. Choose a location to save your project file

And that is it.  
You now have the ability to:
 - Access your entire project from the side bar.
 - Quickly find files in a project (`Ctrl + P`)
 - Quickly find functions in a project (`Ctrl + Shift + R`)
 - Projects can be indexed for quicker code searching (codesearch package)

## PS: 
If you have multiple projects, you can quickly switch between them after adding a new key binding.

 1. `Ctrl + Shift + P`
 1. Type and Select `Preferences: Key Bindings`
 1. For the User Key Binding, add `{ "keys": ["ctrl+alt+p"], "command": "prompt_select_workspace" }`
 1. Now you can use `Ctrl + Alt + P` to switch between projects.

## PSS: 
If you also choose to use Sublime, you will want/desperately need [Package Control](https://packagecontrol.io).