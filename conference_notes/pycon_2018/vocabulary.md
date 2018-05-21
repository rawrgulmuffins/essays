# Goal
This document covers all words that I didn't know going into the conference.
Hopefully I'll get around to either linking to definitions for said words or
writing down the definition I received at PyCon itself.

# Impedance Mismatch
[This was used in the context of talking about the scenario when the same tool
(or file or format, etc.) is used to solve more than one problem and those
solutions contradict themselves.](https://en.wikipedia.org/wiki/Object-relational_impedance_mismatch)

# Top Type and Bottom Type; Sub-Type and Super-Type
This was used in the Type-checked Python in the Real World talk.

# Structural sub-typing vs Nominal sub-typing
* In inheritance something is nominally a sub-type because it has used the
inheritance system in the language to become a sub-type.
* Structural sub-typing is the case where something is a sub-type because it has
the expected methods of the given type. An example of this is `iter` expects
that a structural sub-type contains a `def __next__():` and `def __iter__():`.

# Singular Value Decomposition
[Wiki Page](https://en.wikipedia.org/wiki/Singular-value_decomposition)
[Talk That is entirely focused on describing what this means.](https://youtu.be/d7iIb_XVkZs)

# Latent Feature
[Used in this talk; describes machine learning features which are unknown to
the programmer before the model is trained.](https://youtu.be/d7iIb_XVkZs)

# Cosign Similarity (Cosign distance)
* A means of comparing the distance between two vectors. This is useful if
you're using SVG to produce latent features. Then you can do vector operations
and comparisons between the latent features in your problem space.

# Noun: Surprise
* A SVG training library. The example used in the talk used the MovieLens
dataset

# Noun: MovieLens
* A three column dataset that's commonly used in machine learning examples. It
contains users, movie titles, and ratings.

# Noun: agithub
* A Mozilla backed (poorly named) project that's used to support CLI clients
that map to REST APIs.

# Feature Flags:
Global boolean values which are used to turn features on and off so that you
can turn off bad features without releasing a new version of your application.

# Automanual Testing (Example Testing)
[Reference](https://youtu.be/MYucYon2-lk?t=200)
* This is referring to tests that are using specific example input and specific
example output

# Noun: Hypothesis (Python library)
* This is a property based testing on the input and output types for a
function. I've heard multiple people state that it's the best testing library
potentially in any language.

# Noun: modsimpy.com

TODO: Fill in

# Pytorch

TODO: Fill in

# cnn

TODO: Fill in

# rnn

TODO: Fill in

# Flat Buffers

TODO: Fill in

# Simd

TODO: Fill in

# Noun: Apache Arrow

TODO: Fill in

# PyBind11

TODO: Fill in

# aiomultiprocess
[Python Library](https://github.com/jreese/aiomultiprocess). It's the same idea
as multiprocess but it uses Asyncio (if you're code isn't blocking) for I/O
instead of blocking I/O.

# Noun: Enforce.py
* Library to assert python types at runtime.

# Noun: Waspy
* Transport agnostic framework whose goal is to let things like Django and
Flask run on more than HTTP.

# Noun: Skulpt.py

TODO: Fill in

# research operationalization
[Wiki Link](https://en.wikipedia.org/wiki/Operationalization)
[Talk Usage](https://youtu.be/KAPeaEJeuc8?t=876)
The usage seems to be about how do you break down intangible concepts into
something that can be recorded.
