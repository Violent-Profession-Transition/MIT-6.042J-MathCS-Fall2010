## Number theory

Number theory is the study of **integers**: _all the variables in number theory are taking integer values, ie domain of discourse is Z_

## quotient and remainder

**The Division Theorem: there exists unique numbers `q, r` such that `a = qb + r` and `0<= r < b`**

`q` = quotient(a, b)

**we use the notation `qcnt(n, d)` for quotient**

`r` = remainder(a, b)

**we use the notation `rem(n, d)` for remainder**

For example, `qcnt(2716,10) = 271` and `rem(2716,10) = 6`

## divisibility

`c` divides `a` `(c | a)` IFF `a = k * c` for some `k`

There are a variety of synonyms for `c divides a`:
- `a` is a multiple of `c`
- `c` is a divisor of `a`

`n | 0` , any number divides 0 because `0 = 0 * n`, 0 is a multiple of every number

if `c|a` and `c|b`, then `c|(a+b)`

In fact, if `c|a` and `c|b`, then `c|(sa+tb)`

## Primality Testing

Determine whether a number is prime. In 2002, a simple new method was discovered by Agrawal, Kayal, and Saxena, which showed that prime testing only required a polynomial number of steps

## Factoring

Given the product of two large primes `n = qp`, there is no efficient way to recover the primes `q` and `p`.

The best known algorithm is the "number field sieve"

## integer linear combinations

`sa + tb` is integer linear combinations of `a` and `b`, **c divides an integer linear combinations of `a and b`**

**`c` is a common divisor of `a and b`. Common divisors of `a & b` divide integer linear combinations of `a & b`**

## Greatest Common Divisor (GCD)

The greatest common divisor of `a & b`exists by the Well-Ordering Principle, because **it is a set of non-negative integers with an upper bound** (1 is always a common divisor)

- gcd(10, 12) = 2
- gcd(13, 12) = 1
- gcd(17, 17) = 17 _The GCD of n and n is always n_
- gcd(0, n) = n, for n > 0
- gcd(p,a) = 1 or p, for prime p _The only divisors of `p` are +-1 and +- p_

## Die Hard Water Jug Problem

In particular, how can one form `g` gallons using jugs with capacities `a` and `b`?

Suppose that we have water jugs with capacities `a` and `b` with `b>=a`, assuming that b-jug is big enough

At every step, the amount of water in each jug is of the form `sa + tb`, for some integers, s and t, an **integer linear combination of a and b`**


_Key action: pour water from one jug to another until one is empty or the other is full_

**Invariant property in jug problem: The amount of water in each jug is always a linear combination of a and b (the capacities of the jugs)**

Corollary: water jugs with capacities 3 and 6 cannot form 4 gallons of water. The amount in each jug is always of the form `s*3 + t*6`, and is always a multiple of 3. 4 is not a multiple of 3.

## Linear Combinations and the GCD

_The GCD of a and b is equal to the smallest positive linear combination of a and b_

Proof: By Well Ordering Principle, there must be a smallest positive linear combination of a and b; call it `m`. `gcd(a,b)<=m` and `m<=gcd(a,b)` => m = gcd(a,b)

_gcd(a,b) is an integer linear combination of a and b, `gcd(a,b)  = sa + tb`_

If we want to characterize the linear combinations of a and b, they are precisely the multiples of the GCD of a and b, since `gcd(a,b) | sa + tb`

## Euclidean Algorithm

The efficient way to compute the GCD of two numbers is based on a classical algorithm: Euclidean algorithm

**GCD Remainder Lemma**:
`gcd(a,b) == gcd(b, rem(a,b))`, for `b != 0`

Proof: `a = qb + r` => any divisor of `(a, b)` or `(b, r)` or `(a, r)` must also divide `(a, b, r)` => `(a, b)` and `(b, r)` have the SAME divisors => same greatest divisor (all their divisors are the same)

Example a=899, b=493
gcd(899, 493) = gcd(493, 406) = gcd(406, 87) = gcd(87, 58) = gcd(58, 29) = gcd(29, 0) = 29

## Die Hard and GCD

`gcd(1147, 899) = 31`, so there is no way to obtain 2 gallons of water using jugs of capacities 1147 and 899, since we can only obtain multiples of 31 gallons with these jugs.

`gcd(26,21) = gcd(21, rem(26,21)) = gcd(21, 5) = gcd(5, rem(21, 5)) = gcd(5, 1) = 1`, so it is possible to make 3 gallons using 21- and 26-gallon jugs

There exists integers `s` and `t` such that `3 = s*21 + t*26`

Repeat these two steps until X gallons, which must happen eventually:
1. Fill the smaller jug
2. Pour all the water in the smaller jug into the larger jug, if at any time the larger jug becomes full, empty it out, and continue pouring the smaller jug into the larger jug

This two-step method eventually generates **every multiple of the greatest common divisor of the jug capacities**

## State Machine and Euclidean Algorithm

It is good exercise in state machine thinking and pratice in program verification to reformulate the Euclidean algorithm as a **state machine**

The states of the state machine will be pairs of non-negative integers. `NxN`, the Cartesian product of the non-negative integers

```
States ::= N x N
start ::= (a,b)
state transition defined by
    (x, y) => (y, rem(x, y)), for y!=0
```

**gcd(x, y) is a constant, therefore a preserved invariant is gcd(a,b) == gcd(x,y)**

The state machine has only one trasition rule, and ths transition preserves the GCD

At termination, `x = gcd(x, 0) = gcd(x, y) = gcd(a,b)`

## Extended Euclidean Algorithm | Pulverizer

**the pulverizer allows us to find coefficient s and t, given a and b**

The pulverizer is very close to Euclidean algorithm, thus commonly known as "the extended Euclidean GCD algorith"

The Pulverizer goes through the same steps as Euclidean algorithm, but requires **some extra bookkeeping along the way: as we compute gcd(a,b), we keep track of how to write each of the remainders as a linear combination of a and b**

- x = ca + db
- y = ea + fb
- rem(x, y) = x -qy = ca + db -q(ea + fb) = (c-qe)a + (d-qf)b

Pulverizer always works and it terminates. You can "pulverize" very large numbers very quickly. Pulverizer's speed makes it a very useful tool in the field of cryptography.

