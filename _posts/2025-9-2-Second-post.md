---
layout: post
title: Vacuous truth
tag: Mathematics
---

## This post is about vacuous truth and why I think its cool

Before going into what this is about, I will first try to explain a bit about formal logic.

The base of formal logic lies in two assumptions (and probably more):  
* [law of excluded middle](https://en.wikipedia.org/wiki/Law_of_excluded_middle), which simply states that a statement can only be true or false
* the assumption that a statement cannot simultaniously be true and false. 

The vacuous truth pops up in a simple conditional:  
Lets say we have the conditional statement *if P then Q*, (\\(P \to Q\\)), where P and Q are statements that obey the two assumptions, then the truth table would be the following:

\\[\begin{array}{c|c|c}
P & Q & P \to Q \newline
\hline
T & T & T \newline
T & F & F \newline
F & T & T \newline
F & F & T
\end{array}\\]

I want to talk about each row separately: 
1. This makes sense intuitively as if both P and Q are true then intuitively \\(P \to Q\\) is also true
2. This row also makes sense as if P is true and Q is false, then 