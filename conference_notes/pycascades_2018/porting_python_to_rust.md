# RaspberryPy to RustyPi: Porting a Python module to Rust (Anna Liao)

# Rust Community Initiatives
* "Rust Reach" RipGrep
* Impl Period: Mentors for newbies "e-easy" github issues

# What is Rust?
* Fast, Safe, concurrent.
* Made for "frustrated C++ programmers"
* Mozilla (Servo / Quantum)

# Rules For Programming Experiments
1. It doesn't have to be good
2. It doesn't have to work
3. But, you have to learn something

# Thoughts on Rust itself
* Articles from 2015 probably don't apply anymore in rust.
* Stack vs heap is a thing in Rust.
* Some stack only times are Path, &str (string slice), array
* some heap applicated types are: Pathbus, ?, and vectors

# Ownership
* Two variables with ownership that's shared on the heap mean things won't
compile. This means you need to clone heap data if you want all variables to
share heap data. This does mean that you could potentially get data races
because of the different variables.
* docs.rust-lang.org/book
* getting-started-with-the-sense-hat
* Learning computer architecture with Raspberry Pi

