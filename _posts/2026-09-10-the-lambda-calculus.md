---
layout: post
title: The Lambda Calculus
date: 2026-09-10 15:18 +0800
---
## Intro - Language, Dependent Type, and Proof Helper

Recently I come across a pretty language called Agda, a *dependent-typed* programming language as well as a *proof helper*, which is earlier and has less syntax-sugar than Lean.

The dependent type system, which means types may rely on value indices, provides the language with the ability to carry out proofs leveraging the principle of Curry-Howard correspondence. For example:

```
+-elim : m + n ≡ m + r -> n ≡ r
+-elim {zero} refl = refl
+-elim {suc m} p = +-elim (suc-injective p)
```

where

- `m`, `n`, `r` are *values*;
- `≡` is a *family of types* indexed by two values;
- `m + n ≡ m + r` and `n ≡ r` are *types*, i.e. *proposition* or *witnesses*;
- The function `+-elim` provides strategy for constructing proposition `n ≡ r` given the witness `m + n ≡ m + r`, and is thus a *proof*.

Dependent type system is not our topic, at least for today. There has to be an underlying untyped "programming language" for the type-theory and any other PL theory to grow upon. It is the *lambda calculus*.

## Formalization of Programming Languages, with Functions

When looking at rules within lambda calculus, we should see them as parts of a *constructive proof* that computation can be done with pure functions.

The grammar of lambda calculus is as simple as

```
t ::= x     -- variable
    | λx.t  -- abstraction
    | t t   -- application
```

### Binds and Scopes

In abstraction `λx.t`, the parameter `x` is a binder who binds any free occurrence of `x` within its scope `t`.

### Operational Semantics

---

## References

- [Types and Programming Languages](https://www.cis.upenn.edu/~bcpierce/tapl/), Benjamin C. Pierce