# wget

My favorite download manager :D

## Simple one-off small download

```bash
$ wget <url>
```

## Continuing the download
Larger files require the ability to be continued, so run the command below:

```bash
$ wget --continue <url>
```

And if the download fails, you can `^C` and re-execute it to continue the download.

## Limiting the rate

Usually, I don't want my downloads to interfere with the overall internet bandwidth so I can continue using internet without my network speed declining dramatically. So I use it like this:

```bash
$ wget --continue --limit-rate=500k
```

So it limits the download rate to 500kps.

## Downloading from a file of links

Put one link per line in a text file and feed it to `wget` like so:

```bash
$ wget --continue -i ./links.txt
```

It will, one by one, attempt to download the links, and if it has downloaded some of the files before (let's say you interrupt it and continue the download again by executing the command once more), then it will skip over them.
