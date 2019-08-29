# Vim Navigation
Simple navigation (instead of arrow keys):
```
 k
h l
 j
```

- Instead of page down, `Ctrl + f` and instead of page up, `Ctrl + b`.
- `z + enter` keeps cursor but moves text (similar to emacs' Ctrl + l)
- `w` considers puctuations as word
- `W` simply considers space as separator between words
- `b` same for back
- `B` again just considers space as separator
- `0` begining of line
- `^` goto first char of line
- `<num>gg` goto that line
- `<num>G` goto that line again
- `gg` goto begining of file
- `G` goto end of file
- `:1` goes to first line
- `:25` goes to line 25th
- `:$` goes to end of file
- `Ctrl + g` gives a status line
