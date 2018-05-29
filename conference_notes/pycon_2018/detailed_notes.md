# Goal
This document will cover my thoughts on the talks, keynotes, and lighting talks
at PyCon 2018. Please note that there's the [vocabulary.md page](No Link Yet) that covers
words (including proper nouns) I heard at PyCon and didn't know. In addition,
any medium to large sized concept that I thought should have some additional
exploration is in the [concepts.md page.](No Link Yet)

# All Talks
https://www.youtube.com/channel/UCsX05-2sVSH7Nx3zuk3NYuQ/videos?flow=grid&sort=p&view=0

# Most Useful Talks
All of these talks have more detailed notes later on in this document.

## Hillel Wayne - Beyond Unit Tests: Taking Your Testing to the Next Level 
[Full Talk](https://www.youtube.com/watch?v=MYucYon2-lk&t=13s)
* This is my favorite talk of the conference.

## Alex Gaynor - Learning From Failure: Post Mortems
[Full Talk](https://www.youtube.com/watch?v=L9Y2ap6vIMg)

## Elizabeth Wickes - Hard Shouldn't be Hardship: Supporting Absolute Novices to Python
[Full Talk](https://www.youtube.com/watch?v=KAPeaEJeuc8)

## Allison Kaptur - Love your bugs
[Full Talk](https://youtu.be/HuuYwUxM-ZY)

## Carl Meyer - Type-checked Python in the real world - PyCon 2018
[Full Talk](https://www.youtube.com/watch?v=pMgmKJyWKn8)

## Nina Zakharenko - Elegant Solutions For Everyday Python Problems
[Full Talk](https://www.youtube.com/watch?v=WiQqqB9MlkA)
* I think this is a great video if you're coming to Python from another
language

## Kyle Knapp - Automating Code Quality
[Full Talk](https://www.youtube.com/watch?v=G1lDk_WKXvY)

# Conversation Notes
This section contains notes I took from conversations at PyCon

TODO: Fill out this section after some research.

# Spark References
* "Pyspark and TensorFlow are just bindings. They're not actually python APIs"

## Mezos vs Yarn vs Kubernetes
* Multiple people said that the biggest advantage of Yarn is being able to have
the HDFS data local to the Yarn containers. Mezos doesn't have the ability
apparently? A common sentiment was that if you need to upgrade from Yarn to
Mezos that it's better to move to Kubernetes. I didn't get a lot of explanation
for why.

## Appache Arrow
* Apparently PySpark pickles every row in a DF to do serialization rather than
batching all rows (or per column) before doing pickle. I was told they use 
pickle instead of cpickle?!
* Apache arrow avoids having to pickle per row in a data frame if you want to
serialize from JVM to python.Holden stated that pickle serialization is
basically guaranteed to be our biggest pipeline bottleneck.


## Books and Blogs referenced During the Talk
Steven Lott - function friendly programming
http://simonmar.github.io/posts/2017-01-24-asynchronous-exceptions.html
https://blog.sentry.io/2016/10/19/fixing-python-performance-with-rust
https://medium.com/yanda/getting-up-to-speed-on-crypto-195e5d494bb7
https://www.youtube.com/watch?v=ctffjzdgGvc


## Open Spaces
### Trio
* trio.testing
* pytest-trio.autojump_clock
* RFC 6555

# Lighting Talks
I'll try to boil down the essences of each lighting talk into something
generally useful.

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
### AREPL
[Full Talk](https://youtu.be/c-I0md_3fbQ?t=20)
* A real-time python evaluator.
* The idea is that you have a REPL that runs your code as you type it so that
you can see errors without having to go to the command line.

### Blinky's Async Adventure
[Full Talk](https://youtu.be/c-I0md_3fbQ?t=992)
* This is the best specific example of what asyncio is.

### Type Hinting
[Full Talk](https://youtu.be/c-I0md_3fbQ?t=1347)
* Asserting Python types at runtime.
* Enforce.py is a library that does this.

### A Class is a Poor Mans Loop?
[Full Talk](https://youtu.be/c-I0md_3fbQ?t=1599)
* This talk is an abomination. =P

### RIP HTTP
[Full Talk](https://youtu.be/c-I0md_3fbQ?t=1894)
* This talk is about using protocols other than HTTP for service to service
communication. I couldn't agree more with this talk.
* My vote is use AMQP for service to service communication.

### Modeling and Simulation in Python
[Full Talk](https://youtu.be/c-I0md_3fbQ?t=2174)
* This talk was about a professor talking about how he wants to change college
education such that more people graduate with engineering degrees. Apparently
half of the degree applicants drop out in their first year.

### Baysian Hacking With Python
[Full Talk](https://youtu.be/c-I0md_3fbQ?t=2698)
* "Is a billion simulations proof of correctness?" =P
* The idea behind this talk is interesting. Basically, if you don't have the
math background to prove the probability of certain events you can simulate the
results with a large number of iterations to get a good enough estimate.
* My biggest problem with this talk is that it doesn't talk about the expected
rate of incidence. If you expect one instance in a billion and only run a
billion iterations then you're not going to get a good estimate.

### Make The Web More Pythonic
[Full Talk](https://youtu.be/c-I0md_3fbQ?t=3704)
* This talk is about using Skulpt.js and stateless python functions to do
client side python that works both on the server and the client.

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
* [Blog post written by Ned on the
topic](https://nedbatchelder.com/text/slowsgrows.html)


## Adapting from Spark to Dask: what to expect
### Dask Cons
* No JSON support
* No Parquet support
* Not the full list of Pandas Aggregations
* No SQL syntax
* Cluster deployments are "work in progress" according to the presenter
* No built in Kerberos support.

## John Reese - Thinking Outside the GIL with AsyncIO and Multiprocessing
[Full Talk](https://www.youtube.com/watch?v=0kXaLh8Fz3k)
* The use case is fetching data from https endpoints at a large scale.
* According to Facebook Asyncio gets massive performance gains over threads for
the use case. Massive was "orders of magnitude".
* Multiprocess lets you get parallel CPU time with co-routines for I/O.
* If you want to use this I highly suggest watching this talk since some
assembly is required.
* [Benchmarks of different strategies](https://youtu.be/0kXaLh8Fz3k?t=1123)
* One question was why not use message queues? The answer was using
multiprocess and asyncio allows you to deploy a single binary or to know
anything about the network being used on.

## Elizabeth Wickes - Hard Shouldn't be Hardship: Supporting Absolute Novices to Python
[Full Talk](https://www.youtube.com/watch?v=KAPeaEJeuc8
Tags: Teaching, Learning
As you can see from the note sizes I loved this talk.
* "95%, actual number not made up, of my students who come to learn programming
for librarians are humanities students."
### Standards For Teaching Classes
* Live code for all leactures. No slides.
* Examples must map to homework problems.
* Demonstrate how to solve errors / bugs.
* Include a prediction prompt or formative assessment every 10 minutes.
* Use subgoal labels.
* Share notebooks and lecture notes with students.
* "It's so easy to fall into the geek gene myth. But, it is a myth."

### Critical Questions
* Why aren't students reaching out for help?
* Often times you can save them hours with a few minutes of their time?
* Why do students report that they're stupid?

### Students Are Primed To think
* Programming is hard.
* Crying is normal.
* Help will be crappy.
* Programming comes with stress.

### Students need boundaries for normal.
* "Let me know when you get stuck." This statement needs qualifications for
what stuck means.
* Even things that are tangible are hard to measure. The example given was that
measuring snakes goes from the tip of their nose to their anal opening. The
tails are skipped for clarity reasons.
* [This section of the talk is a really good point](https://youtu.be/KAPeaEJeuc8?t=1096)

### "Pro-Tips"
[Section about setting boundaries](https://youtu.be/KAPeaEJeuc8?t=1194)
* Banned the world stupid. Particularly in self-reference.
* Two hour rule. If you aren't making progress after an hour take a half hour
break. If you still aren't making progress after another half hour ask for
help.
* Students still say that the two hour rule "allows them" to ask for help. Even
with all of the qualifications about being able to ask for help students still
struggle with it. They're really primed to assume that programming is going to
be an awful experience.
* "The first time a student reaches out to you it's a test of trust."
* If you want students to have questions you need to give them time. Be visibly
distracted or disinterested while waiting for students to think of questions.

## Pieter Hooimeijer - Types, Deeper Static Analysis, and you
[Full Talk](https://youtu.be/hWV8t494N88)
Tags: Security, Type Checking, Static Analysis
* Presentation by the PYRE dev.
* [Example of a security problem caught by type
checker](https://youtu.be/hWV8t494N88?t=187)
* [Longer blog post about real world vulnerability](https://www.grepular.com/Abusing_HTTP_Status_Codes_To_Expose_Private_Information)
* This is a great definition of what [static analysis
is](https://youtu.be/hWV8t494N88?t=373)
* [Goal of a buttom up type checker](https://youtu.be/hWV8t494N88?t=802)
* The consequences of a buttom up analyzer is that the order of the type
checking matters and that you need a scheduler in order to complete things in
parallel.
* "This approach doesn't require new type annotations to work but it does
require you to have a security engineer who can give you a list of sources and
sinks that you're interested in."
* [Numbers on PYRE use at Instagram](https://youtu.be/hWV8t494N88?t=1296)
* Question: Do you find that because the buttom on analyzer needs to make a
call stack that shows all functions calling all functions you find issues that
aren't actually possible.

Answer: Your checker should never actually do all functions to all functions.
You should start at a main entry point and as closely follow the actual call
graph as possible.

* Question: "How do you deal with functions that deal with shared state?"
Answer: "The talk is a lie." You need to worry about more than just input and
output. We use things called 'access paths' that check the total state space,
input, and output while looking at how the input modifies the state space. For
security issues just looking for sinks and sources is enough of an improvement
over grep that it's worth using.
* Question: Have you published your scheduler?
Answer: No
* Question: Are there similarities to taint analysis and profiling? Can you do
both in one pass?
Answer: Both profiling and taint analysis are very hard domains and we have
tried to do both at the same time. Having tried it we don't recommend that
anyone else tries to. You should use different tools for each problem.

## Nathaniel J. Smith - Trio: Async concurrency for mere mortals
[Full Talk](https://www.youtube.com/watch?v=oLkfnc_UMcE)
tags: Concurrency, Asycio, Intro

## Alex Gaynor - Learning From Failure: Post Mortems 
[Full Talk](https://www.youtube.com/watch?v=L9Y2ap6vIMg)
tags: Software Engineering, Post Mortems, Best Practices, Management
* This talk is about how to learn from operational failures. "If it's something
you would measure with an SLA it's an operational failure."
* ["If you leave here having learned absolutely nothing else I want you to walk
away believing that 'holding people accountable' (aka firing them) and making
systemic improvements are unrelated problems and maybe even mutually
exclusive"](https://youtu.be/L9Y2ap6vIMg?t=206)
* The goal should be blameless post-mortems.
[Example](https://youtu.be/L9Y2ap6vIMg?t=272)
* "Using passive voice subtly conveys 'we blame someone if we know who it was.
We're keeping this information secret because deep down we want someone to
blame."
* [How Complex Systems fail](https://how.complexsystems.fail)
* [What does a Post-mortem look like](https://youtu.be/L9Y2ap6vIMg?t=511)
* [Post Mortem Markdown Template](https://youtu.be/L9Y2ap6vIMg?t=620)
* Incidence reports should contain as much objective information as possible.
The analysis should be the portion that contains subjective information.
* Examples of subject information are "What of the possible solutions to this
incident which ones are the most important to do first."
* "If you dig down into 'computers were a mistake' you are probably going too
far"
* It's always important to include the portions of your process that worked
correctly (like your deployment process).
* It's important to change your language form "root cause" to "root causes."
* Table top exercises; Interesting to simulate an issue to work on process
improvements. Not always useful for finding underlying bugs.
* It's totally ok to redefine what an incident is.
### Non-Software Examples
* NTSB (National Transportation Safety Board). Accident investigations vs
criminal investigations. You want your post-mortems to mimic the NTSB rather
than an insurance company whose primary goal is to assign blame.
* The NTSB uses what it calls "The Party System" to improve transportation
safety.
### Misc Information
* Even if you don't know why a incident happened you should still do a
post-mortem.
* "Human error" should almost never be used as a reason. This claim better mean
"It's too rare and it's too costly to fix the other systemic issues here."
* "If you don't fix classes of bugs at the root then you will end up generating
more classes of bugs faster than you can fix them. As time advances, your
product will become more and more unreliable as more systemic errors are
added."
* "Fixing bugs systemically is cheaper than fixing them one at a time."

### Q&A
* Question: How do you transition a culture from a blameful culture to a
blameless culture?
Answer: It is my belief that only really leadership can start this transition
and if a culture is already in a blameful mode that might not be enough.

* Question: Is it helpful to have executive representation in a post-mortem?
Answer: It can be helpful but it's more important to have people directly
involved with fixing the issues.

## Stacy Morse - Code Reviews Using Art Critique Principles
[Full Talk](https://www.youtube.com/watch?v=lpWvYxEW09k)
tags: Code Review, Management, Software Engineering,
### Art Critiques Methodology
* [Rules for critique](https://youtu.be/lpWvYxEW09k?t=491)
* Code reviews are about the code and not the person.
* Code reviews should be ready to be reviewed. WIPs aren't useful.
* You must stay neutral.
* Constructive criticism only. Defined later.
* Stay on topic. If you want to design something different or gripe about a
different commit / module take it somewhere else.
* Mandatory participation. You must be reviewed and be reviewed.
* Thumbs up is not a code review. There's no proof that the code was reviewed.
There's no responsibility sharing.

### Pre Code Review
[Section](https://youtu.be/lpWvYxEW09k?t=737)
* run ALL of your tests.
* Check all requirements.
* Identify your work.

### Code Critique Stages
[section](https://youtu.be/lpWvYxEW09k?t=815)
* Description
    * identify, Inventory, Neutral. Just read the code.
    * It's hard to describe what the inventory is. My interpretation is
    comments on a PR that show that you've read the code.
* Analysis
    * new code + old code
    * facts needed for critical interpretation.
* Interpretation
    * Taking the two previous stages and putting them together.
    * It's your responsibility to do this without blame.
* Judgement
    * Can the code ship?

### Constructive Criticism
[Definition](https://youtu.be/lpWvYxEW09k?t=1353)

### Q&A
Question: How do you evaluate sunk costs when giving someone a code review.
Answer: If the change would substantially improve the code you should make the
change. That's an organization question, however.

Question: Is it worthwhile to implement a code of conduct for code review?
Answer: I have implemented them before but it's hard to use a template for
code review.

Question: Can you give us a specific example of an art critique?
Answer: The presentor did a open space with a specific example that was
unrecorded.

## Dmitry Filippov, Ewa Jodlowska - By the Numbers: Python Community Trends in 2017/2018
[Full Talk](https://www.youtube.com/watch?v=xEE4X-9RROM)
* This is an interesting talk but I don't know if there's anything really
actionable from it. I do think [this
section](https://youtu.be/xEE4X-9RROM?t=680) on there being more data scientist
than web developers is interesting.
* (75% python3 adoption](https://youtu.be/xEE4X-9RROM?t=934)

## Esther Nam - One weird trick to becoming a better software developer
[Full Talk](https://www.youtube.com/watch?v=IYWlfVqBQLc)
* This is an interesting talk that tries to give you specific exercises to work
on the kinds of cognitive empathy required to be a better developer.


## Kyle Knapp - Automating Code Quality
[Full Talk](https://www.youtube.com/watch?v=G1lDk_WKXvY)

## Matt Davis - Python Performance Investigation by Example
[Full Talk](https://youtu.be/yrRqNzJTBjk)
* Collect data, analyze, experiment, goto Collect
* cprofile, line_profiler, pyflame, plop, nylas-perftools. The last three are
made to be profilers with low overhead that run in produce instances.
* `python -m cProfile -o output_file my_script.py`
* In a Jypter notebook `%%prun -q -D output_file`

### Viewing data
[pstats example](https://youtu.be/yrRqNzJTBjk?t=685)
* `pstats.Stats('profile.cprof')`
* [snakeviz example](https://youtu.be/yrRqNzJTBjk?t=773)
* ["Going with math instead of state tracking got us a factor of 100 
improvement in speed"](https://youtu.be/yrRqNzJTBjk?t=1134)

## Irina Truong - Adapting from Spark to Dask: what to expect
[Full Talk](https://www.youtube.com/watch?v=X4YHGKj3V5M)
* [What is Spark](https://youtu.be/X4YHGKj3V5M?t=159)
* [What is Dask](https://youtu.be/X4YHGKj3V5M?t=187)
* [Performance Benchmark](https://youtu.be/X4YHGKj3V5M?t=873)
* [Example of Dask visual feedback](https://youtu.be/X4YHGKj3V5M?t=1224)
* [Dask drawbacks](https://youtu.be/X4YHGKj3V5M?t=1310)

# All Posters
https://www.flickr.com/photos/129877449@N07/sets/72157693710700302/

## Reproducible Environments for Machine learning using Docker Layers
https://www.flickr.com/photos/129877449@N07/42128542031/in/album-72157693710700302/
