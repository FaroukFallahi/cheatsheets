# Regex basics

These are the very basics of regex.

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

