# FFmpeg Commands

## Convert video

```sh
ffmpeg -i <input.ext> -c copy <out.ext>
```

## Convert video and copy all tracks

```sh
ffmpeg -i <input.ext> -map 0 -c copy <out.ext>
```

to exclude incompatible streams

```sh
ffmpeg -i <input.ext> -map 0 -map -0:s -c copy <out.ext>
```

to re-encode incompatible streams

```sh
# To re-encode audio
-c:a <codec>
# To re-encode video
-c:v <codec>
```

## To move moov to start for streaming files

```sh
-movflags +faststart
```

```sh
ffmpeg -i <input.ext> -c copy -movflags +faststart <out.mp4>
```

## Extract subtitles

```sh
ffmpeg -i <input.ext> -map 0:s:0 subs.ass
```

## Add subtitles (burn)

```sh
ffmpeg -i <input> -vf subtitles=<filename> <output>
```

## Extract JPEG from frame at a given time

```sh
ffmpeg -ss hh:mm:ss -i <input> -vframes 1 -q:v 2 screenshot.jpg
```

## Extract audio from video

```sh
ffmpeg -i <input> -map 0:1 audio.ac3
```
