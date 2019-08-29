# Transform and Substitute

- `I` to enter insert mode at the begining of the line (where ^ takes you not 0)
- `a` to enter insert mode right after the current character
- `A` to enter insert mode at the end of the line
- `o` to enter insert mode in the next line
- `O` to enter insert mode in the prev line

To repeat an insert just preceed it with the desired number
- `70i*<esc>`
- `5o#<esc>`

To see the brilliance of this, try this: `10o10.11.12.<esc>`. Now you have
10 lines starting with 10.11.12. which you can use to complete multiple ip
addresses.

## Replace
- `R` to enter replace mode
- `r` to replace one character with the character entered after this r
- `c<motion>` to delete <motion> (like a word when using w) and place you
in insert mode
- ex: `c$hello<esc>`

Also it gets an optional register prefix, for instance: `"acw` to save the
deleted word in the `"a` register in case we need it later.

Focus that d$ deletes til the `eol`, now D does that too. Now to make it
intersting, `c$` deletes til `eol` and places you in insert mode hence `C`
should do that too :)
- `cc` change the whole line
- `~` changes the lower to upper case and vice versa
- `g~<motion>` changes all the way to `<motion>`
- ex: `g~w`
- ex: `g~$` (same as `g~~`)
- `U` forces upper case (like to uppecase this: thisISawesome)
- so we can do: `gUw`
- we also have: `gUU` to uppercase an entire line
- for lowercase: `guw`
- and: `guu`

We can use J to join lines together, like if you have this:
```
hi
hello
```
Go on the hi and press J, it becomes: `hi hello`.

If the first line has a dot at the end, it adds two spaces (genius vim):
```
3.
14
```
We could use `gJ` to prevent the space addition and of course `J` accepts
preceeding `<num>`.
