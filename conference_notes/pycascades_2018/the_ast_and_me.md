# The AST and Me (Emaily ?)
* Is Python compiled or interpreted? Yes.
* Life cycle is SourceCode -> parse -> ParseTree -> 

# Primary Tools For AST Delving
* `ast` and `dis` modules, `astor`, `meta`, `codegen`

# Python Peephole optimization
* Double negatives are turned into the same as no negatives
* `Not a in not b` turns into `a in b`
* Constant folding is also an optimization

# How Does The AST affect your code?
* Practical applications of knowing about the AST are:
* Improve and speed up your code by looking at the bytecodes.
* If you are refactoring something you can ensure that no behavior actually
changed by ensuring that the AST is the same between 
* Change the Python Grammar
* Round-tripping
* Code generators
* Alternatives Interpreters
