# Goal
This document will cover my thoughts on the talks, keynotes, and lighting talks
at PyCon 2018. Please note that there's the [vocabulary.md page](No Link Yet) that covers
words (including proper nouns) I heard at PyCon and didn't know. In addition,
any medium to large sized concept that I thought should have some additional
exploration is in the [concepts.md page.](No Link Yet)

# All Talks
https://www.youtube.com/channel/UCsX05-2sVSH7Nx3zuk3NYuQ/videos?flow=grid&sort=p&view=0

# All Posters
https://www.flickr.com/photos/129877449@N07/sets/72157693710700302/

# Most Useful Talks
All of these talks have more detailed notes later on in this document.

## Carl Meyer - Type-checked Python in the real world - PyCon 2018
[Full Talk](https://www.youtube.com/watch?v=pMgmKJyWKn8)

## Nina Zakharenko - Elegant Solutions For Everyday Python Problems
[Full Talk](https://www.youtube.com/watch?v=WiQqqB9MlkA)
* I think this is a great video if you're coming to Python from another
language



# Big Concepts
This section covers big ideas that I think have the potential to shift or
change ones everyday life. They tend to be less practical in the short term but
might be more useful long therm than the previous section.

# Personal Notes
This section contains notes I took from conversations at PyCon and wrote into a
slack channel. That's a long way of saying it's not super organized but I think
they're important enough to flush out a little.

# Lighting Talks
I'll try to boil down the essences of each lighting talk into something
generally useful.

## Thursday Night
## Friday Morning
## Friday Night
## Saturday Morning
[All Talks](https://www.youtube.com/watch?v=VJ0vibC_Hl0)
### Giving Thanks
* pip install thanks
* CLI tool that lets you put a dependency name in and get links to how the
maintainers want to receive funding.
### Penetration Testing The Developer Interview
* Attack the interview process
* Heuristic == Vulnerability in this setting
* Talent.works/blog
* Apparently action-verb resumes get twice as many call-backs as a numbers
based resume according to the presenter.
* Applying on Monday has a 5 times higher call-back rate.
* Stories are more engaging than a list of information. Your goal is to have
your resume tell a story.
### DataLad - Versioning Your Data
[Full Talk](https://youtu.be/VJ0vibC_Hl0?t=1338)
* git-annex allows you to set things like Google Drive and S3 as remote
repositories.
* Datalad allows you to treat individual remotes as subsets of data and treat
some repositories as supersets.
* [Here's an example repo that uses
Datalad](https://github.com/djarecka/full_dataset)
* Datalad uses "web symbolic links" where the git repository contains links to
the data but not the actual data.
## Saturday Night
## Sunday Morning

# Full Talk Notes
The talks in this section are the ones that I watched and found at least a
portion of it noteworthy. That doesn't mean other talks don't have important
things in them I just probably haven't seen them.

## Kenneth Reitz - Pipenv: The Future of Python Dependency Management
[Full Talk](https://www.youtube.com/watch?v=GBQAKldqgZs)
* This talk starts on the history of Python packaging. I don't think you need to
know most of this and you can probably skip to this
[point](https://youtu.be/GBQAKldqgZs?t=607) to know how
pipenv works.
* This talk can be boiled down to "Use pipenv and pipfile instead of virtualenv
and pip directly to have a better dependency story."
* Kenneth postulates that the lock files that other modern languages uses in
their packaging systems is the main point of difference that makes other
system much easier to use from the user perspective.
* The lack of distinction between top level required dependencies and the lower
level dependencies of your top level dependencies. Another way to put this is
that if you have a `requires.txt` file and it just includes `flask` without a
bound version it's non-deterministic installs. In addition if you bound flask
to `flask==1.0.1` it's still non-deterministic because of flasks dependencies.
* The new Pipfile format uses the same solution as Cargo or NPM (a lock file
with dependency resolution).
* One thing to note about Python packing vs say Go or NPM is that Python
packaging is very much a set of individuals vs something like NPM where there is
a company that manages the language packing system. I think this is the largest
reason why Python packing has lagged behind other modern languages.

## Mario Corchero - Effortless Logging: A deep dive into the logging module
[Full Talk](https://www.youtube.com/watch?v=Pbz1fo7KlGg)
* The [Common Misuses](https://youtu.be/Pbz1fo7KlGg?t=657) section is worth
watching
* The [Buffering and non-blocking section is totally worth
watching](https://youtu.be/Pbz1fo7KlGg?t=1228)
* This talk covers how the Python logger works. I think if you have read the
Python docs on the logger you probably know all of the content of this talk.
* I think the visualizations of the control flow for the logger should be added
to the Python docs.

## Carl Meyer - Type-checked Python in the real world - PyCon 2018
[Full Talk](https://www.youtube.com/watch?v=pMgmKJyWKn8)
* `Typing.Optional` isn't something I knew about but the presenter suggests
avoiding optionals for return types since it allows for Nones which requires if
checks at run time.
* Using `typing.overload` allows you to define two functions where one can
return `None` if given certain arguments and one returns whatever type for when
you get the expected input. This is cleaner.
* `typing.TypeVar` allows for things like 
`AnyStr = TypeVar('AnyStr', str, bytes)` which produces cleaner interfaces.
* One interesting way of describing the `any` type is that it's both a sub-type
and a super-type.
* Using the `typing_extensions import Protocol` to do type checking on Python
duct-typing sounds amazing to me. This sounds particularly amazing if you want
to make objects that follow either a Python protocol (`len`, `iter`) or a third
party protocol (`gtk.render`).
* Again, it's my personal belief that the biggest benefit of Pythons typing
system is documentation of the codes behavior.
### Escape Hatches
* Python typing has a ton of escape hatches in case you actually want dynamic
behavior (such as dynamic routing
* `# type: ignore`, `from typing import cast` and `pyi files` are all ways of
telling pythons type checker to ignore or modify its behavior.
### Gradual Typing
* Simple ground rule: Only functions with annotations are considered to have a
type. Everything else is `any -> any`.
* When you're ready to work on stuff you simple add annotations. Normally you
type your most used files first.
* Instagram has released a tool called `Monkeytype` which allows for you to
run a program and save the used types for a all the functions called. You can
either save them in pyi files or have Monkeytype auto-annotate.
* Apparently Facebook's `Pyre` type checker took about 45 seconds to type check
Instagram's codebase vs the 5 minutes of Mypy.

## Jason Huggins - Keynote
[Full Talk](https://www.youtube.com/watch?v=q-x7jK72E6E)
* This talk is all about how to run a kids school technical program such that
you can have one robot per child.

## Jake VanderPlas - Performance Python: Seven Strategies for Optimizing Your Numerical Code
[Full Talk](https://www.youtube.com/watch?v=zQeYx87mfyw)
* This talk is totally worth listening too especially if you care about
performance with Python. It doesn't really cover string performance, however.
Mainly vectors and matrices that have floats or ints.
* Standard Python runs at about a factor of 100 times slower on repeated
operations compared to Fortran.

## Daniel Pyrathon - A practical guide to Singular Value Decomposition in Python
[Full Talk](https://youtu.be/d7iIb_XVkZs)
* One thing I walked away from this talk with is a question. How do you
determine the number of latent features you want to use with SVG?
* This was a great explanations for how to use a very common feature used in
Machine learning.

## Nina Zakharenko - Elegant Solutions For Everyday Python Problems
[Full Talk](https://www.youtube.com/watch?v=WiQqqB9MlkA)
* This was a pretty good overview of how to make Python that feels good (using
things like magic methods, the Python protocols, iterators, generators, etc.)
* I think this is a great video if you're coming to Python from another
language
* Using context managers to yield feature flags is an excellent idea.

## Ned Batchelder - Big-O: How Code Slows as Data Grows
[Full Talk](https://www.youtube.com/watch?v=duvZ-2UK0fc)
* Ned Batchelder is one of my favorite presenters. I've learned so much from his
other talks. You should check them out.
* This is probably an refresher to anyone whose taken an algorithms class. If
you haven't taken an algorithms class this definitely worth your time.
* "How your code slows as your data grows."
* [This section about specific time complexities in python is useful to
watch](https://youtu.be/duvZ-2UK0fc?t=1082)
* "Fancy algorithms are slow when n is small and n is usually small"
* [Blog post written by ned on the
topic](https://nedbatchelder.com/text/slowsgrows.html)