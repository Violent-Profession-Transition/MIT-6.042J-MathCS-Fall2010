## Inference Rules

Logical deductions or _inference rules_ are used to prove new propositions

a fundamental inference rule is **modus ponens**, this rule says that a proof of P + a proof of P IMPLIES Q, is a proof of Q

## Proof by cases

Some philosophers (**intuitionists**) think reasoning by cases is worrisome:

Is P == NP?
P = polynomial time
NP = non-deterministic polynomial time

Proof typically begin with the word "Proof" and end with sort of doohickey like:
口 == checked == QED

## Proof by Contradiction

*rational number is something that can be expressed as the ratio of two integers*

**when you do a proof by contradiction, always start off by saying, by contradiction** write down (by Cont)

**assume for the purpose of contradiction**, that not P is True.

sqrt(2) = a/b (a fraction in lowest term, a and b have no common divisors)

`a is even` => `(2 | a)` two divides `a`

contradiction == `#`

**It is important to remember that when you start by assuming NOT(P), you cannot rely on the intermediate results after a proof by contradiction is completed, such as the several lemmas built up from the proof by contradiction**

## Proof by Picture

People often make the mistake in graphs, proof by picture, they draw it and it looks like this, you accept that, and then it is game over. The mistake is right up front, "I drew it wrong"

## Axiomatic methods

- important True propositions are called *theorems*
- A *lemma* is a preliminary proposition useful for proving later propositions
- A *corollary* is a proposition that follows in just a few logical steps from a theorem

Euclid's axiom-and-proof approach, now called *axiomatic method*, remain the foundation for mathematics today.

## ZFC

A handful of axioms, called the Zermelo-Fraenkel with Choice axioms (ZFC), together with a few logical deduction rules, appear to be sufficient to derive essentially all of mathematics.?!

ZFC axioms are important but are too primitive. A formal proof in ZFC that 2+2=4 requires more than 20,000 steps!

The ZFC axioms avoid Russell's paradox because they imply that no set is ever a member of itself

## Sets

There is no notion of an element appearing more than once in a set **(multisets can have elements occur more than once, but multisets are NOT ordinary sets)**

## Popular Sets

- N = non-negative integers
- Z = integers
- Q = rational numbers
- R = real numbers
- C = complex numbers

## disjoint

two sets, A and B, are said to be _disjoint_ iff they have no elements in common.

It is the same as saying A is a subset of the complement of B

## cardinality

the _cardinality_ of a set A is the number of elements in A and is denoted by `|A|`

## the power set P(A)

the set of all subsets of a set A == the power set P(A)

More generally, if A has n elements, then there are `2**n` sets in P(A)

In other words, **if A is finite, then |P(A)| == `2**|A|`**

## Set builder Notation

**Define a set using a predicate => set consists of all values that make the predicate True**

For example, `A ::= { n <- N | n is a prime and n = 4k + 1 for some integer k}`.

The set A consists of all non-negative integers n for which the predicate "n is a prime ...  k" is True. Thus the smallest elements of A are: `5, 13, 17, 29, 37, 41, ...`

Trying to indicate A by listing first few elements wouldnt work very well, even after many terms the pattern is still not obvious!

## Induction

**induction is by far the most powerful and commonly used proof techniques in computer science**

**Induction is really just an axiom**, but a reasonable axiom.

The reason induction is an axiom is the **`and so on forever part`**

1. Whenever you prove by induction, first thing you write down is "proof by induction"
2. Then figure out what is your predicate, your inductive hypothesis, what is `P(n)`
3. Check the **Base case**
4. Inductive step
5. Assume `P(n)` is True, for purposes of induction or for purposes of verifying the inductive hypothesis (just to let us know why you are assuming it, in other words you are no assuming P(n) is true for purposes of contradiction)

Assuming what we are trying to prove, we are trying prove that P(n) is true for all n, and we just assumed it. **But we are assuming it in the context of establing that `P(n) => P(n+1)` is true**, then we apply the induction axiom to conclue P(n) is True for all n.

**Often induction gives you NO HINTS, NO ANSWERS, just prove that it is right after you have a clever idea to the answer**. Figuring out the inductive hypothesis or the answer is hard, but the proof by induction is not hard.

## Ellipsis (...)

The dot dot dot means you need to fill in the pattern here, **which is vague!**

If `n = 1`, `1 + 2 + ... + n = 1`
If `n <= 0`, `1 + 2 + ... + n = 0` (... notation is very ambiguous)

## Make stronger `P(n)`

Easier to prove something that is harder. When `P(n)` gets more powerful, you get more to assume in the inductive step.

**Sometimes, if you have got more tools, it becomes easier to prove even a harder thing**

**If you dont succeed at first with induction, dont try again, try something harder**

**It is the art of picking a good inductive hypothesis, ie the predicate P(n), such that `P(n) => P(n+1)`**

Strengthening the induction hypothesis is often a good move when an induction proof won't go through. **BUT keep in mind that the stronger assertion must actually be True**.

**Finding just the right induction hypothesis requires trial, error and insight**

The key turned out to be finding an extremely clever induction hypothesis, P(n)

