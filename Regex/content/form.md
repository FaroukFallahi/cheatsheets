# form
These are regexes that are useful in different sort of forms in programming.

## Email
```
^\w+([.-]?\w+)*@\w+([.-]?\w+)*(\.\w{2,3})+$
```
Starts with a mandatory chunk of "word" allowing more chunks to follow with optional
dots or dashes in between them (optionally). Then the @ is required following
by another set of the same pattern. Afterwards, it requires at least a pattern of
two to three "word" characters preceded with a dot.
