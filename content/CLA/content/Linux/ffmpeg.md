# ffmpeg

## get file information

```bash
$ ffmpeg -i ./input
```

## webm to mp3

```bash
$ ffmpeg -i ./input.webm -vn -ab 128k -ar 44100 -y ./output.mp3
```

## convert video to gif

```bash
$ ffmpeg -i ./input.mkv -f gif ./output.gif
```
## Trim a video by time:
```bash
$ ffmpeg -i input.mkv -ss 01:32:33.0 -c copy -to 01:35:21.0 output.mkv
```

## Convert video to mp3:
```bash
$ ffmpeg -i input.mkv -vn -f mp3 output.mp3
```
