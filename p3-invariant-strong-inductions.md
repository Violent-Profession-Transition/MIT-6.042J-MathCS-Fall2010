## Good proofs

Good proofs are correct, complete, clear, brief, "elegant", well-organized, in order
(for example use lemmas the same way you would use subroutines in writing code)

## Invariant

Invariant is a very powerful and commonly used concept in computer science, very closely tied to induction.

In order to show your system can never reach a particular special state, it is sufficient to show there is some property called the invariant that holds at the initial state, and is preserved by every legal move, and is not present, does not hold, in that special state.

**Invariant proofs are always by induction. The invariant and inductive hypothesis become one and the same**

Our inductive hypothesis is that `P(n)` after any sequence of `n` moves, `n` is the number of moves you took to get there, from the start state, the parity of the number of inversions is odd. That is the inductive hypothesis, and it is same as the invariant.

## Strong Induction

Strong induction is similar to ordinary induction, but it can be easier to use when solving certain problems.

**Like regular induction, strong induction can be expressed with an axiom -- strong induction axiom**

**In strong induction, you get to assume a lot more**

Any proof you can do with strong induction you can do with ordinary induction, but ordinary induction might be harder to use. **You cannot prove any more with it, but it makes your proof much easier**

With strong induction, you get to assume all these P(0, 1, 2,..) are true in order to prove `P(n+1)`, as part of the inductive step.
