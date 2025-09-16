---
layout: post
title: Vacuous truth
tag: Mathematics
---

## This post is about vacuous truth and why I think its cool

Before going into what this is about, I will first try to explain a bit about formal logic.

### The assumptions
The base of formal logic lies in two assumptions (and probably more):  
* [law of excluded middle](https://en.wikipedia.org/wiki/Law_of_excluded_middle), which simply states that a statement can only be true or false
* the assumption that a statement cannot simultaniously be true and false. 

### What is a statement?
```
A statement is something that can only be true or false, 
e.g. David is super cool - statement as can either be true or false (most likely true)
e.g. How do I become cool, David? - not a statement as you can't say if its true or false,  
simply doesnt make sense
```

### The four constructions of statements
Assume P and Q to be statements obeying the assumptions  
We can form new statement out of P and Q using the following constructions: 

#### Conjunction
The conjunction denoted by \\(P \land Q\\) is basically the same as the AND logic gate, where:
\\(P \land Q\\) is __true__ only when both P and Q are __true__  
*Logic gate:*
\\[\begin{array}{c|c|c}
P & Q & P \land Q \newline
\hline
T & T & T \newline
T & F & F \newline
F & T & F \newline
F & F & F
\end{array}\\]
#### Disjunction
The disjunction denoted by \\(P \lor Q\\) is basically the same as the OR logic gate, where:
\\(P \lor Q\\) is __true__ when either P or Q is __true__, or both are __true__.  
*Logic gate:*
\\[\begin{array}{c|c|c}
P & Q & P \lor Q \newline
\hline
T & T & T \newline
T & F & T \newline
F & T & T \newline
F & F & F
\end{array}\\]
#### Negation
The negation of P is denoted by \\(\lnot P\\), this is also the same as the NOT logic gate, where:
\\(\lnot P\\) is __true__ whenever P is __false__  
*Logic gate:*
\\[\begin{array}{c|c}
P & \lnot P \newline
\hline
T & F \newline
F & T
\end{array}\\]
#### Conditional
The conditional of P and Q is the equivalent of saying "If P then Q", and is denoted by \\(P \to Q\\), where:  
\\(P \to Q\\) is __false__ ONLY when P is __true__ and Q is __false__  
*Logic gate:*
\\[\begin{array}{c|c|c}
P & Q & P \to Q \newline
\hline
T & T & T \newline
T & F & F \newline
F & T & T \newline
F & F & T
\end{array}\\]

---
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
1. This makes sense intuitively as if both P and Q are true then P leading to Q is also true
2. This row also makes sense as if P is true and Q is false, then 

