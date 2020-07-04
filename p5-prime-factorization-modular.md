## Fundamental Theorem of Arithmetic OR Unique Prime Factorization

_Every natural number can be factored as a product of primes_ (used to prove unique prime factorization), we just have to prove that the product of primes is unique.

If p is prime, and `p | a1a2...am`, then `p | ai` for some `i`.

Every positive integer can be written in a **unique way** as a product of primes.

```
Every integer n > 1 has  a unique factorization into primes:
p1. ... . pk = n
with p1 >= p2 >= ... >= pk
```

61394323221 = 53 * 37 * 37 * 37 * 11 * 11 * 7 * 3 * 3 * 3

You will always get exactly this sequence, this weakly decreasing sequence of primes

## Prime Number Theorem

Let f(x) be the number of primes less than or equal to x, for example f(10) = 4 because 2, 3, 5 and 7 are primes less than or equal to 10.

Prime numbers are irregularly distributed, so the growth of f(x) is similarly erratic. However, the **Prime Number Theorem gives an approximate answer: about one integer out of every `ln x` in the vicinity of x is a prime (about one in lnx is a prime)**

The Prime Number Theorem was conjectured by Legendre in 1798.

## How many digits before finding a 10-digit prime?

Would you have to look through thousands or millions or billions of digits of `e` to find a 10-digit prime? **The rule of thumb derived from the Prime Number Theorem says among 10-digit numbers, there is about 1 prime in every `ln 10^10 = 23`**, so there should be about 1 prime in every 23 10-digit numbers.

Sure enough, the first 10-digit prime in consecutive digits of `e` appears quite early.

## Turing Code with Prime Number

In 1936, Turing wrote "On Computable Numbers, with an Application to the Entscheidungsproblem". With this model, Turing proved that **there exists problems that no computer can solve, no matter how ingenious the programmer**

### Turing's Code (text into integer)

Replace each letter of the text with 2-digit, for example, "victory" becomes: 22 09 03 20 15 18 25

Turing's code requires the message to be a prime number, so we need to pad the result with a few more digits to make a prime. In this case, pad with 13 gives prime: 2209032015182513 is a prime.

### Encryption `m` with `m*`

`m` is the unencoded message (which we want to keep secret), `m*` is the encrypted message (which the Nazis may intercept), and `k` is the key

Beforehand: The sender and receiver agree on a secret key, which is a large prime `k`

Encryption: the sender encrypts the message by `m* = m * k`

Decryption: the receiver decrypts `m*` by `m*/k = mk/k = m`

For example, k  = 22801763489, and message `m` is "victory" padded with 13 = 22090320151825.

```
m* = m * k
= 22090320151825 * 22801763489
= 50369825549820718594667857
```

### Primality Test with AKS and Probabilistic algorithms

AKS algorithm for primality test was proved in 2002 which can determine primality in about (log n)^12 steps.

12th degree polynomial grows very fast, so AKS procedure is of no practical use.

**There is no practical need to improve AKS algorithm since very efficient _probabilistic_ procedures for prime-testing have been known since the early 1970s**

These probabilistic procedures have some probability of giving a wrong answer, but the probability is very low.

### Integer Factoring Difficulty

The Nazis see only the encrypted message `m* = mk`, so recovering the original message `m` requires factoring `m*`. Despite immense efforts, no efficient factoring algorithm has ever been found. **In effect, Turing's code puts to practical use his discovery that there are limits to the power of computation**

### Breaking Turing's Code with GCD

However, when the sender transmits a 2nd message using Turing's code and the same key `k`. This give Nazis two encrypted messages to look at:

```
m1* = m1 * k
m2* = m2 * k
```

The GCD of the two encrypted messages `m1*` and `m2*` is the secret key `k`. The GCD of two numbers can be computed very efficiently. **So after the second message, the Nazis can recover the secret key `k` and read every message!**


## Modular Arithmetic

Gauss introduced the notion of **congruence: a is congruent to b modulo n iff  n | (a-b)** (definition of modular arithmetic), n > 1. _the definition using remainder (remainder lemma) is an equivalent formulation_

```
a ≡ b (mod n)
```

For example 29 ≡ 15 (mod 7) because 7 | (29 - 15) = 7 | 14

Congruence is a relation between two numbers, a and b

**There is a close connection between congruences and remainders: `a ≡ b (mod n)` iff `rem(a,n) = rem(b,b)`**

**Congruence modulo n is a congruence relation, meaning that it is an equivalence relation that is compatible with addition and multiplication**

`a ≡ b (mod n)`'s (mod n ) means this (mod n) applies to the entire equation. **This notation is NOT to be confused with the notation `b mod n`, which refers to the modulo _operation_**

### Modulo Operation

`b mod n` is the unique integer `a` such that 0 <= a < n and a ≡ b (mod n)

## Congruence modulo n as Partition of the integers

Congruence modulo n defines a partition of the integers into n sets **so that congruent numbers are all in the same set**

For example, for modulo 3, we partition the integers into 3 sets:
```
{..., -6, -3, 0, 3, 6, 9, ...}
{..., -5, -2, 1, 4, 7, 10, ...}
{..., -4, -1, 2, 5, 8, 11, ...}
```
according to whether their remainders on division by 3 are 0, 1, or 2

**When arithmetic is done modulo n, there are only n different kinds of numbers to worry about, because there are only n possible remainders**

## Congruences work a lot like equations (ordinary equaliy)

```
a ≡ b (mod n) and c ≡ d (mod n) => a+c ≡ b+d (mod n)
a ≡ b (mod n) and c ≡ d (mod n) => ac ≡ bd (mod n)
```

You can freely substituting any number by a number that it is congruent to, and the final congruence result of the formula is unchanged

**congruence and `a ≡ rem(a,n) (mod n)` keeps `(mod n)` arithmetic in the remainder range, thus keeping the range [0, n)**

## Congruence modulo n tricks

666666663 ≡  7878787687623 (mod 10), because the substraction of two numbers ending in 3 is divisible by 10


`a ≡ rem(a,n) (mod n)`, which **basically allows us whenever we feel like it to replace numbers by their remainders**

```
287^9 ≡ ? (mod 4)

since rem(287,4) = 3
287^9 ≡ 3^9 (mod 4)

3^9 = 9^2^2 * 3
since rem(9, 4) = 1
3^9 ≡ 1^2^2 * 3 (mod 4)

therefore
287^9 ≡ 3 (mod 4)
```

## When Congruence mod n is NOT like ordinary arithmetic

### No Arbitrary Cancellation

k is cancellable (mod n) iff k has an inverse (mod n) iff gcd(k,n) =1 or k is relatively prime to n

### Inverse exists for modulo a prime

`7 * 3 ≡ 1 (mod 5)`, so 7 and 3 are multiplicative inverses

All numbers congruent to 3 modulo 5 are also multiplicative inverses of 7, for example `7 * 8 ≡ 1 (mod 5)`

Numbers congruent to 0 modulo n (multiples of n) do not have inverses, much as 0 does not have an invrese over the real numbers

## Turing Code Version 2 using Modular Arithmetic

Beforehand: Sender and receiver agree on a large prime `p`, which may be made public, and used as the modulus for all the arithmetic. Also there is a secret key `k <- {1,2,..., p-1}`

Encryption: message `m` can be any integer <= p-1, message `m`  no longer needs to be a prime. The sender encrypts the message `m` to produce `m*` by: `m* = rem(mk,p)`


