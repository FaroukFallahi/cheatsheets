# ffmpeg

Trim a video by time:
```bash
$ ffmpeg -i input.mkv -ss 01:32:33.0 -c copy -to 01:35:21.0 output.mkv
```

Convert video to mp3:
```bash
$ ffmpeg -i input.mkv -vn -f mp3 output.mp3
```
