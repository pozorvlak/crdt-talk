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
* Hard to achieve

!SLIDE
# CRDTs

* op-based
* state-based

!SLIDE
# Semilattices

* poset (S, ≤)
* *join* operation ∨ : S × S → S

!SLIDE
# Examples

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

!SLIDE
# LVars

!SLIDE
# Examples

!SLIDE bullets incremental
# Differences

* LVars: determinism
* CRDTs: availability
* Can be unified
