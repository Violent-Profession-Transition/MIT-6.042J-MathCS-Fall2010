# Chapter 1: Propositions

Definition. A **proposition** is a statement that is either true or false.

## How to talk about mathematics

To get around the ambiguity of English, mathematicians have devised a special mini-language for talking about logical relationships. This language mostly uses ordinary English words and phrases such as “or”, “implies”, and “for all”. But mathematicians endow these words with definitions more precise than those found in an ordinary dictionary.

## Compound Propositions

use variables such as _P_ and _Q_ in place of specific propositions

The understanding is that **these variables, like propositions, can take on only the values T(true) and F (false).**

a truth table indicates the true/false value of a proposition for each possible setting of the variables

So if a mathematician says, “You may have cake, or you may have ice cream,” he means that you could have both

## Implies

`p => q` is True, if `p` is False or `q` is True

**An implication is true exactly when the if-part is false or the then-part is true.**

p implies q `==` not q implies not p

## IFF (if and only if) 

IFF = `<=>` = `=>` + `<=`

**check implications both ways**

## Propositional logic in computer programs

Propositions and logical connectives arise all the time in computer programs.

```java
if ( x > 0 || (x <= 0 && y > 100) )
...
```

Let A be the proposition that `x > 0`, and let B be the proposition that `y > 100`. `A OR (NOT(A) AND B)` == `A OR B`

This means we can simplify the code into:
```java
if ( x > 0 || y > 100 )
...
```

Rewriting a logical expression involving many variables in the simplest form is both difficult and important. Simplifying expressions in software can increase the speed of your program. 

Chip designers minimize the number of analogous physical devices on a chip. The payoff is potentially enormous: a chip with fewer devices is smaller, consumes less power, has a lower defect rate, and is cheaper to manufacture.

## Predicates and Quantifiers

Some propositions are easy to check by a simple Truth table (A and B, P and Q)

But **some propositions may involve a large or infinite number of possible cases.**

**`::=` means equal by definition (assignment)**, it is ok to write `=` instead of `::=`

There are many examples of propositions that seem to be true when you check a few cases (or even many), but which turn out to be false. The key to remember is that you can’t check a claim about an infinite set by checking a 
finite set of its elements, no matter how large the finite set

**Propositions that involve _all_ numbers are so common that there is a special notation for them, "for all"**

Euler (pronounced “oiler”)

computer scientists are often interested in propositions concerning the “correctness” of programs and systems, to determine whether a program or system does what it’s supposed to do.

## Predicates

A _predicate_ is a **proposition whose truth depends on the value of one or more variables**

predicates are often named with a letter. Furthermore, a function-like notation is used to denote a predicate supplied with specific variable values
```
P(n) ::= "n is a perfect square"
```
P(4) is True, but P(5) is False

**If _P_ is a predicate, then P(n) is either true or false, depending on the value of n**

## Quantifiers

Always True (for all, for every, _universally quantified_) vs Sometimes True (there exists, _existentially quantified_)

## Axioms

propositions assumed to be True

- Axioms should be **consistent**
	- a set of axioms is consistent if **no proposition can be proved to be both true and false** (axioms as a group)
- Axioms should be **complete**
	- a set of axioms is complete if it can be used to **prove every proposition** is either true or false

it is IMPOSSIBLE to get a set of axioms that satisfy both consistency and completeness

**If you want consistency, and that is a must, there will be true facts that you will never be able to prove**

## Validity

A propositional formula is **valid** when it evaluates to True no matter what truth values are assigned to the individual propositional variables.

The same idea extends to predicate formulas, it must evaluate to True no matter what values its varibles may take over _any unspecified_ domain, and no matter what interpretation a predicate variable may be given.

Examples of valid assertions:
- Distributive Law  P AND (Q OR R) == (P AND Q) OR (P AND R)
- rule of negating a quantifier
- there exists x, for all y, P(x, y) is True => for all y, there exists x, P(x, y) is True _(P is a binary predicate, for example, P(x, y) mean x divides y)_

## Satisfiability

A Proposition is **satisfiable** if _some setting of the variables_ make the proposition True. For example, `P AND NOT(Q)` is satisfiable because the expression is True if P is True and Q is False. But `P AND NOT(P)` is not satisfiable because the expression can never be True for any setting of P.

## SAT

The general problem of deciding whether a proposition is satisfiable is called _SAT_

SAT  = Satisfiability

Given a Boolean formula over `n` variables, can you set the variables to make the formula True?

SAT is one of the first problems to be proven to be NP-complete.

## XOR

The value of (P XOR Q) is True IFF **exactly one** of P and Q is True.

## Equivalence

Two propositional formulas are **equivalent** IFF they have the **same** truth values in **all environments**

One example is DeMorgan's Law

## SAT vs VALID

To check that `G` is _valid_, can check that `NOT(G)` is _not satisfiable_

## for All is like AND

Let `s` range over the set of staff, `P(s) ::= [s is pumped about the course]`

For All `s`, `P(s)` is the same as:
P(a) AND P(b) AND P(c) AND ... AND P(z)

## there exists is like OR
