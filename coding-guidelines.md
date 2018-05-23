<!-- TITLE: An Introduction to Software Style Guides -->

# The Motivation of Style

First, let me say a little bit about my motivation. I don’t promote style guides because I’m some kind of software despot who wants everyone to program *exactly like me*. These guides are not laws. They’re observations that when code is written a certain way, we introduce fewer bugs, and write more understandable code.

One of the primary reasons we follow the recommendations of a style guide is that __we want to make wrong code look wrong.__ ([Joel Spolsky wrote about this back in 2005][spolsky])

[spolsky]: https://www.joelonsoftware.com/2005/05/11/making-wrong-code-look-wrong/

Put another way, __good style exposes bad patterns.__ Many of the recommendations in the style guides help us recognize when something looks "off." Sometimes they're compulsions we indulge in to demonstrate that we're avoiding a pitfall in the language itself.

We could stop there and be pretty pleased with ourselves, but style guides are more than just how we avoid writing buggy code. Software isn’t something we write once and unleash. We are constantly reading (and re-reading) the codebase to address issues and add features. Another important motivation for code style is that __readability eases comprehension.__ 

Code is the *human interface* to the CPU. When we encounter an area of the codebase that’s unfamiliar, often the only way to understand what’s going on is to read the code. (Ideally we’d have a complete technical specification and good documentation, but we live in The Real World&trade;, and unicorns don’t exist either.) Readable code means we can quickly understand how a new feature fits in with an existing system, or rapidly diagnose a subtle bug.

# Structure of These Guides

We primarily write in Python and JavaScript, so naturally the style guides focus on those languages. The documents in this section cover three main points of coding style and provide recommendations of tools to help keep the codebase maintainable.

First, we look at the syntactic conventions of a language—mundanities like indentation style, line length, and spacing. Rigorous adherence to these conventions speed up our understanding of what the code __*says*__ so we can move on to consider what the code __*means*__.

The second concern of a style guide is the stylistic aspect of code. Here, we’re concerned with naming conventions, documentation formats, and error handling. This is also where we point out semantic practices that can reduce cognitive complexity of code.

After syntax and semantics, style guides also provide a high-level discussion of software architecture patterns that are commonly applied in the code base.

Finally, we provide tool recommendations for automated static analysis. Static analysis tools can help identify a number of subtleties you may have missed when writing your code. The tools also have limitations. The tool section of a style guide lays out some of the recommended processes for use of these tools.