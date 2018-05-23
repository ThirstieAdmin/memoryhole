<!-- TITLE: Coding Guidelines -->

Sometimes it's good to be oppinionated.
# Python
Many very smart developers with many more years of experience have written about code style before us.
Their work is a good place to start.

- [PEP 8 – Style Guide for Python Code][pep8]
- [Code Style *The Hitchiker's Guide to Python*][hhgp]

Let's get the specifics out of the way first.

## Indentation
Use four spaces per indentation level.

## Maximum Line Length
We're less strict than PEP 8 here.
We all have screens that are wider than 80 characters and access to text editors that can wrap lines cleanly without breaking them.
Therefore, we prefer lines to have fewer than 80 characters, but we won't reject pull requests if there are 120-character long lines.

## Line Breaks Around Binary Operators
Complex expressions using binary operators should place the line break before the operator.

```
# Bad: 
cart_total = (subtotal +
              (subtotal * tax_rate) -
              discount +
              delivery_fee +
              tip)
```

```
# Good:
cart_total = (subtotal
              + (subtotal * tax_rate)
              - discount
              + delivery_fee
              + tip)
```

[pep8]: https://www.python.org/dev/peps/pep-0008/
[hhgp]: http://docs.python-guide.org/en/latest/writing/style/

# JavaScript
Don't even bother; it's all garbage no matter what.