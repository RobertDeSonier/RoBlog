---
layout: post
title: SOLID: The Liskov Substitution Principle
date: xxxx-xx-xx 07:00:00
categories: solid architecture
---

Wanting to explore SOLID outside the OO lens.  
Bringing more clarity to fellow Devs.


## Definition:

*What is wanted here is something like the following substitution property: If for each object o1 of type S there is an object o2 of type T such that for all programs P defined in terms of T, the behavior of P is unchanged when o1 is substituted for o2 then S is a subtype of T.* - Barbara Liskov

## But what does it really mean:

LSP is easy to under stand the violation than the actual definition of the principle.



The best way to know if you are violating one of the SOLID principles, is to unit test your code.  
You will quickly see a violation of LSP, when you can not just insert a mock of the same type in place of your object used in the system you want to test.

## Examples of LSP outside OO