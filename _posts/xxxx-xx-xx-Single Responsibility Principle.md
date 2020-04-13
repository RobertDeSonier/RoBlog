---
layout: post
title: SOLID: The Single Responsibility Principle
date: xxxx-xx-xx 07:00:00
categories: solid architecture
---

Wanting to explore SOLID outside the OO lens.  
Bringing more clarity to fellow Devs.

When first introduced to SRP, I often hear "How do you define a single responsibility?"  

## Definition:

*A module should be responsible to one, and only one, actor.* - Uncle Bob

## But what does it really mean:

The beauty of Uncle Bob's definition is the clarity of who owns the responsibility and the generic definition of the module.  

*Actor* is the group of people that determine what the change to the system should be and are the owners of that change.  
When the group starts clashing on what the change to the module should be or being inadvertently effected by other members of the group, you are most likely feeling a violation of SRP.  
This is when you need to redefine the actors and provide the correct module to each.

*Module* is a very broad term, and this allows us to provide a more generic approach to the common SRP view of how to write good functions or classes.  
Module can refer not only to functions and classes, but also APIs, libraries, and components.  
With this generic term, everything we create requires an Actor and thus holds value.  

By defining SRP with the terms of *Module* and *Actor*, a requirement arises to produce an entire systems with clear boundaries of ownership.

## Farming for examples:



## Examples of SRP outside OO