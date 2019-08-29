# Create and Delete
CREATE: insert mode

DELETE:
- `x` delete current character
- `X` deletes char before cursor
- `dw` `operation(d) motion(w)`, delete a word
- `dW` deletes one word forward (considers space as separator)
- `db` deletes one word backwards
- `dB` deletes one word backwards (considers space as separator)
- `dl` deletes one char to right (equivalent for x)
- `dh` deletes one char to left (equivalent for X)
- `dj` deletes current and the line below
- `d2j` deletes three lines starting from current downwards
- `dk` deletes current and the line above
- `d2k` deletes three lines starting from current upwards
- `d0` deletes from current char to begining of the line
- `d$` deletes from current char to the end of the line
- `D` shortcut for (D$)
- `dd` deletes the current line
- `3dw` `count(3) operation(d) motion(w)` deletes three words
- `d3w` `operation(d) count(3) motion(w)` deletes three words
- `2d3w` `count(2) operation(d) count(3) motion(w)` delete three words twice
- `.` repeat the previous command
----------------------------------------------------------------------
