# Google
When you are searching in google, you can use these to improve your results.

To search for either `this` or `that`:
```bash
this | that
```

If you're unsure about a certain word in a search query or you may not care if
the synonyms of that word is used instead, then use a tilde:
```bash
~small horse
```

To search within a certain website:
```bash
github.com javascript
```

We can use AROUND() as a placeholder, like when we don't know a part of the
sentense:
```bash
i wanna AROUND(2) hand
```

To use a range of numbers:
```bash
metallica album 2005...2019
```

Searching for title or url:
```bash
intitle:Duel Citizenship
inurl:vim tip
```

To see related websites to a certain query:
```bash
related:pink floyd
```

To find exact phrases in that exact order (literal) use double quotes:
```bash
"A farewell to arms"
```

Combine the previous part with addition sign (+) and you'll get results that
include all the literals (what is inside the quotes) but in different places
of the document:
```bash
"kernel developers" + "running the kernel" + "upgrading your kernel"
```

To exclude certain words:
```bash
kernel linux mac -windows
```

To define or find the roots of words (using google as dictionary):
```bash
define:awesome
```

To specify filetype:
```bash
gnome filetype:pdf
```
