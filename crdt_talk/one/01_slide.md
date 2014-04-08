!SLIDE 
# CRDTs and LVars #

!SLIDE bullets incremental
# The CAP theorem #

* Consistent
* Available
* Partition-tolerant
* (pick two)

!SLIDE
# Eventual consistency

* Every write eventually reflected at every node
* Can remain available

!SLIDE
# Hard to achieve

```
6000 total
5700 acknowledged
3319 survivors
2381 acknowledged writes lost! (╯°□°）╯︵ ┻━┻
469 474 479 484 489 494 ... 3166 3168 3171 3173 3178 3183
```

!SLIDE
# CRDTs

* op-based
* state-based

!SLIDE
# Semilattices

* poset (S, ≤)
* *join* operation ∨ : S × S → S

!SLIDE
# State-based CRDTs

* Semilattice (S, ≤, ∨) of states
* Gossip state to adjacent nodes
* Merge state with message using ∨

!SLIDE bullets incremental
# Examples

* Add-only sets
* Observe-remove (OR) sets
* G-Counter
* PN-Counter
* Last-writer wins (LWW)

!SLIDE
# Why it works

The following are equivalent:

* (S, ≤, ∨) is a semilattice with top element T
* (S, ∨, T) is a commutative idempotent monoid

!SLIDE
# Problems

* Expressing your data in semilattices
* Bandwidth
