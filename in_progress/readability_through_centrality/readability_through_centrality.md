Centralizing information is critical to readability

I was reading an excellent blog on 
[why worst practices should be hard](http://www.haskellforall.com/2016/04/worst-practices-should-be-hard.html)
when I ran into this example.


```
data MyRecord = MyRecord
    { foo :: String
    , bar :: Int
    , baz :: Double
    }

myRecord = MyRecord
    { foo = "Hello"
    , bar = 1
    , baz = 2.0
    }
```
My brain says that the presented syntax is clean but that I originally wanted 
to have the type declarations more centralized to the instantiation.

```
myRecord = MyRecord
    { String :: foo = "Hello"
    , Int :: bar = 1
    , Double :: baz = 2.0
    }
```
This means that you run into the issue of repeating yourself if you use 
`MyRecord` in more than one place. It's an interesting situation where the 1
case is more verbose but the many case is less verbose. On a purely characters
typed in comparison there's 78 extra characters in the first example and 26
additional character pre repetition in the second example so after 4 uses
you’re over stating yourself.

But there's one thing the first example explicitly trades off in favor of
maintainability and that's centrality of information. In the explicit example 
you can see that `”Hello”` is a string, `1` is an int, and `2.0` is a float but
if we were to write the example as you’d see it in the wild:

```
data MyRecord = MyRecord
    { foo :: String
    , bar :: Int
    , baz :: Double
    }

myRecord = MyRecord
    { foo = varriable_1
    , bar = variable_2
    , baz = variable_3
    }
```
You wouldn’t be able to tell the data type if the `MyRecord` definition wasn't
immediately visible (which it probably won’t be in any decent sized project)

Here's a more clean cut example of this concept. It uses the Python
[decorator](https://github.com/hchasestevens/hchasestevens.github.io/blob/master/notebooks/the-decorators-they-wont-tell-you-about.ipynb)
and in my opinion it greatly increases the readability of function registration.


```
def some_function_to_dispatch():
    pass

register(some_function_to_dispatch
```
vs 


```
@register
def  some_function_to_dispatch():
    pass
```

The clarity of this example comes from tying the registration declaration with
the function declaration. You can't remove or reposition the registration 
without switching to the other format or breaking the code. Therefor, If 
you've read the function declaration then you must also be presented with the
registration call.

In this example, without the decorator, it's possible to register the function
at the bottom of the module or potentially in an entirely different part of the
code base. Locality of information is critical to understanding. The more
sections of a code base you have to look at in order to understand a concept,
action, or code path the worse the readability of the source code is.

This doesn't seem like a big deal with small examples like this but when you
start running into large code bases that have many layers of code to slog
through before you get to the bottom of the call stack it becomes very hard to
understand what is happening. I've read a code path that looked like this

```
read an xml file -> get a section of XML -> turn XML into JSON ->
Modify attribute -> read the original xml file -> get a different section ->
turn section into JSON -> return both JSON objects -> combine both JSON objects.
```

The reason this set of calls is so wasteful is because there was about 100 
people who had touched this part of the code base. No one had trolled to the
bottom of this call stack before modifying things. There's a multitude of
failures here but one of them is that the functions at the higher levels
didn't know (or inform anyone) that the lower levels retrieved their data from
the original XML file.


I would argue that the first example with the Haskell code is an example of a 
language choosing maintainability (in this case reducing code repetition) while
trading off readability (locality of information). Off the top of my head I
don't know how you’d choose both given that Haskell prefers static type
definitions for data at compile time. I'm not a language designer (in the same
way that I'm not a lawyer) but to my eyes it looks to me like Haskell made the
right choice in this example.

But they did have to make a choice and it should be understood what you’re
giving up.
