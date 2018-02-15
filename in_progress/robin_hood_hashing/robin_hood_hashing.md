# Preamble

* The probability of a collision is > 1/2 when the table is `sqr(pi*n)` full
(why?)
* A probe is a calculation by the hash function which may or may not result in
a collision.
* A set of probe sequences is the sequence of keys that are visited before
finding the final key for the given value.
* Linear probing is the act hashing the value once and, if there is a collision
, moving down the array (normally one index at a time) until you find a open
index.
* Double hashing is the act of having a second hash function that is used when
the first one has a collision. These kinds of hash functions require that the
second hash function return results that are prime relative to the size of
the buckets in the hash table.
* Unified hashing is the strategy of generating a random index until you find
a open index.

# Comparison of Reordering Schemes
* psl = probe sequence length
* lpsl = long probe sequence length
* upsl = unsuccessful probe sequence length
* lupsl = longest unsuccessful probe sequence length
* The paper compares the expected value (`E|*|`) and variance (`V|*|`) using 
alpha to denote the load factor (`size / max_size`) 

* On Page 10 they're using `1 - alpha` to say how much space is left in the
table.
* `V[x] = E[x^2] - (E[x])^2` which means that if `-alpha^-1 * ln(1-alpha)`
* 1 - something is a thing to pay attention to in probability.
