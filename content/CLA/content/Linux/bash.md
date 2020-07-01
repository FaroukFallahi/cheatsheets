# bash

## Keyboard shortcuts

- `ctrl + c` terminates the current process running in the foreground
- `ctrl + d` terminates the input stream or sends the exit signal
- `ctrl + z` suspends the current running process to background
- `ctrl + l` clears the screen
- `ctrl + s` stops all outputs in the current shell
- `ctrl + q` resumes what the previous command stops
- `ctrl + a` goes to the beginning of the line
- `ctrl + e` goes to the end of the line
- `alt + b` goes back one word
- `alt + f` goes forward one word
- `ctrl + b` goes back one character
- `ctrl + f` goes forward one character
- `ctrl + xx` toggles between the current porsition and the beginning of the line
- `ctrl + d` deletes the current character
- `alt + d` deletes all words from the current position to the end of line
- `ctrl + h` deletes all words from the current position to the beginning of the line
- `alt + t` swap the current word with previous one
- `ctrl + t` swap the two characters before the cursor
- `ctrl + _` undo
- `ctrl + w` cut the word before cursor and put in clipboard (local clipboard used in shell)
- `ctrl + k` cut everything after the cursor and add to clipboard
- `ctrl + u` cut everything before the cursor and add to clipboard
- `ctrl + y` paste what you have put in clipboard just earlier
- `alt + u` capitalize the next word and go to the end of it
- `alt + l` uncapitalize the next word and go to the end of it
- `alt + c` capitalize the character under the cursor and move to the next word (useful for capitalizing every first character of a sentence)
- `ctrl + p` alternative for the up arrow
- `ctrl + n` alternative for the down arrow
- `alt + r` revert the changes you made in the history commands (bash is powerful, isn't it? :))
- `ctrl + r` starting the reverse search in history
- `ctrl + o` commit the search and execute that command
- `ctrl + g` exit this reverse search

## Replace and execute the previous command

Suppose, you executed this command:

```bash
$ ls -l
```

And then, you decide that you wanted to list the hidden files as well:

```bash
$ ^ls^ls -a
```

This causes the following to be executed:

```bash
$ ls -a -l
```

This is more interesting in longer commands:

```bash
$ cp /home/user/todo2 /tmp
cp: cannot stat '/home/user/todo2': No such file or directory
$ ^todo2^todo
cp /home/user/todo /tmp
$ ls /tmp/todo 
/tmp/todo
```

<p class="note">Note that this can be dangerous, use it with caution.</p>
