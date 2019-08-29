# Cut, Copy and Paste
cut, copy and paste == delete, yank and put

By default whatever is deleted will be put in the unnamed register
(default register)

- `dd` delete line
- `x` delete character
- `yy` yank line
- `y2w` yank two words
- `d2w` delete two words
- `p` put after
- `P` put before
- `u` undo
- `Ctrl + r` redo

Register types:
- `unnamed` ""
- `numbered` "0 "1 ... "9
- `named`

To see the registers use: `:reg`
- `""` holds text from d,c,s,x and y operations
- `"0` holds last text yanked
- `"1` holds last text deleted (d) or changed (c)

To put the text in a specific register just preceed the action (like p)
with the desired register (like "0 p to paste what's yanked before). `"_` is
called black hole register which is used to delete anything without affecting
the other registers like unnamed and "1 which will store the deleted text.

Whenever we delete something (when not using the black hole reg) other
previously deleted text will be shifted down one register.

`^J` means the `\n` or end of the line character.

There are 26 named registers from a to z which can be used just like the
numbered ones. for instance: `"a yy` this will put the current line to
the `a` register.

To append to the register, we can use the upper case letter of that register,
for instance: `"A yy` this will append the current line to the `a` register.

We can also delete to registers just like yanking: `"z dw` and append to them
as well: `"Z dd`.

We can view a specific register by typing: `:reg z` and view multiple
registers by `:reg 1mz`. This will show registers `1`, `m`, and `z`.

We can also put multiple times (these will both put the ccontent of register
c, 2 times):
- count reg operator ex: `2 "c p`
- reg count operator ex: `"c 2 p`
