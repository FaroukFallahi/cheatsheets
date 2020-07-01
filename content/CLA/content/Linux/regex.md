# Regex

## Literals
"a" means "a". So literally, what you write is what you mean.
- `a` is a
- `1` is 1

## Special characters
Oposite of the previous. Things that mean something other than themselves.
- `.` is "any character"
- `+` is "one or more"
- `*` is "zero or more"
- `?` is "zero or one"
- `^` is "beginning of line" or "not"
- `$` is "end of line"
- `( )` is for grouping sets of characters
- `[ ]` is for any of the characters in the brackets
- `{ }` is for setting minimum or maximum
- `|` is "or"
- `\` is for escaping these characters that are not literal

## escaping
- `\.` is . literally
- `\+` is + literally
- `\(` is ( literally
- `\\` is \ literally
- ...

`\` is used to mean other characters as well:

- `\n` is "newline"
- `\t` is "tab"
- `\r` is "carriage-return"
- `\nnn` is "up to 3-digit octal number"
- `\xhh` is "two-digit hex code"
- `\uhhhh` is "4-digit unicode"
- `\uhhhhhhhh` is "8-digit unicode"

## sequence of characters
Putting multiple literal characters in a sequence will make a sequence (string).

## other stuff here

...

## Email

```
^\w+([.-]?\w+)*@\w+([.-]?\w+)*(\.\w{2,3})+$
```

Starts with a mandatory chunk of "word" allowing more chunks to follow with optional
dots or dashes in between them (optionally). Then the @ is required following
by another set of the same pattern. Afterwards, it requires at least a pattern of
two to three "word" characters preceded with a dot.

## Numbers

### Octal

```
^[0-7]+$
```

### Hexadecimal

```
^0(x|X)[0-9a-fA-F]+$
```

### Decimal

```
^(0)|([1-9][0-9]*)$
```

### Floating point (with and without exponentiation)

```
^[+-]?(([1-9][0-9]*)|(0)?)(\.[0-9]+)*(e[0-9]+)*$
```

### Complex

```
^[+-]?(([1-9][0-9]*)|(0)?)(\.[0-9]+)*(e[0-9]+)*[+-][+-]?(([1-9][0-9]*)|(0)?)(\.[0-9]+)*(e[0-9]+)*j$
```

