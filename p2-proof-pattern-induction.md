## Proof by Contradiction

*rational number is something that can be expressed as the ratio of two integers*

**when you do a proof by contradiction, always start off by saying, by contradiction** write down (by Cont)

**assume for the purpose of contradiction**, that not P is True.

sqrt(2) = a/b (a fraction in lowest term, a and b have no common divisors)

`a is even` => `(2 | a)` two divides `a`

contradiction == `#`

口 == checked == QED

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

**It is the art of picking a good inductive hypothesis `P(n) => P(n+1)`**
