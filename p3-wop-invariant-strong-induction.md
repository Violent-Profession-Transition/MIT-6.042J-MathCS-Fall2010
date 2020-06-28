## Good proofs

Good proofs are correct, complete, clear, brief, "elegant", well-organized, in order
(for example use lemmas the same way you would use subroutines in writing code)

## Methods Useful for All Natural Numbers

- Well Ordering Principle
- Induction Rule
- Strong Induction

These methods are useful when you need to prove that a predicate is True for all natural numbers.

## Well Ordering Principle

**Every _non-empty_ set of _non-negative_ integers has a _smallest_ element**

- must be non-empty set: it is False for empty set which has **no smallest element** because it has NO elements at all!
- must be non-negative integers: it is False for sets of negative integers, and also False for non-negative **rationals**
    - The positive rationals are not Well Ordered: The subset `{1, 1/2, 1/4, 1/8, 1/16, ...}` has no least element.
    - An equivalent statement is that no infinitely descending chain `a0>a1>a2>a3>....` can exist.
    - **A set of numbers is well ordered when each of its nonempty subsets has a minimum element.**
- WOP captures something special about the non-negative integers
- WOP provides **one of the most important proof rules in discrete mathematics**
- **Key: "assume a smallest element/counterexample/where predicate fails, m <- C"**, usually by finding c <- C wtih c < m, contradiction

### example of WOP on m/n

for any positive integers m and n, the fraction m/n can be written in lowest terms, that is, in the form of m'/n' where m' and n' are positive integers with no common factors. How do we know this is always possible? (Predicate P(n) ::= any rational or fractions can be expressed in lowest terms)

Suppose there were m, b <- Z+ such that m/n cannot be written in lowest terms. Let C be the set of positive integers that are numerators of such fractions, and m <- C, so C is _non-empty_. By Well Ordering, there must be a _smallest_ integer m0 <- C, so there must be a m0 such that m0/n0 cannot be written in lowest terms.

This means that there must be a common factor p, p > 1, m0/p, the numerator is also in C, but m0/p < m0, which contradicts the fact that m0 is the _smallest_ element of C. Therefore counterexample to P(n) does not exist. QED

## example of WOP on natural number as product of primes

- Assume C is the set of all integers > 1 that cannot be factored as a product of primes.
- C is _non-empty_, so n <- C, and n is the _smallest_ element, by WOP
- A prime itself is considered a product of prime, so n cannot be prime
- So n must be a product of two integers j and k, where 1 < j,k < n
- **Since j and k are smaller than the smallest element n in C, j and k are no in C** (n is the smallest such number that is not a prime product)
- j and k are therefore product of primes
- n = j * k = product of primes, contradiction QED

## Recipe for WOP

A Well Ordering Proof starts with the assumption that the set of counterexamples is not empty. It then follows that this set must have a smallest element, by the Well Ordering Principle. Much of the math focuses on showing that the set is empty or that there is another element in the set of counterexamples that is even smaller than the smallest element.

## Well Ordering Principle VS Induction

Well Ordering Principle and the Induction Rules are closely related. We can take any Well Ordering proof and reformat it into an Induction proof, and vice versa.

Induction and WOP are rephrasing of the same logical principle. _Which to use is a mater of taste_

## Invariant

Invariant is a very powerful and commonly used concept in computer science, very closely tied to induction.

Invariants are useful in systems that have a _start state (or starting configuration)_ and a well-defined series of _steps_ during which the system can change state (state machines)

In order to show your system can never reach a particular special state, it is sufficient to show there is some property called the invariant that holds at the initial state, and is preserved by every legal move, and is not present, does not hold, in that special state.

**Invariant proofs are always by induction. The invariant and inductive hypothesis become one and the same. We typically use induction to prove that a proposition is an invariant.**

Our inductive hypothesis is that `P(n)` after any sequence of `n` moves, `n` is the number of moves you took to get there, from the start state, the parity of the number of inversions is odd. That is the inductive hypothesis, and it is same as the invariant.

## Strong Induction

Strong induction is similar to ordinary induction, but it can be easier to use when solving certain problems.

**Like regular induction, strong induction can be expressed with an axiom -- strong induction axiom**

**In strong induction, you get to assume a lot more**

Any proof you can do with strong induction you can do with ordinary induction, but ordinary induction might be harder to use. **You cannot prove any more with it, but it makes your proof much easier**

With strong induction, you get to assume all these P(0, 1, 2,..) are true in order to prove `P(n+1)`, as part of the inductive step.
