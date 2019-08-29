# Tricks
To move all images that are also exported to tif to a directory:
```bash
$ mkdir to_move; for filename in $(ls *.tif | cut -d'.' -f1); do mv $filename* to_move; done
```

To convert a bunch of .mp4 files into .mov:
```bash
$ find . -type f > filenames.txt; mkdir converted; for filename in $(cat filenames.txt); do ffmpeg -i $filename -c:v dnxhd -profile:v dnxhr_hq -pix_fmt yuv422p -c:a pcm_s16le ${filename}.mov ; mv ${filename}.mov converted; done
```
