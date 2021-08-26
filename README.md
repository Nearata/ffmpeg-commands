# FFmpeg Commands

> FFmpeg commands i use that forget about

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
