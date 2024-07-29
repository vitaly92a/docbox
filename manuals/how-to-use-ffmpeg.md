# How to use FFMPEG?

FFmpeg is a powerful multimedia framework that can be used to record, convert, and stream audio and video files. Here are some useful tricks to help you get the most out of ffmpeg:

## 1. Convert video to GIF

You can use FFmpeg to convert a video file to an animated GIF. The command uses "-vf" to specify a filtergraph that applies various filters to the video. The filter "scale" is used to resize the video to a width of 320 pixels and maintain its aspect ratio. The "split" filter is used to send the video stream to two outputs, one to create a palette and the other to use that palette to generate the GIF. Here is an example command:

```bash
ffmpeg -i input.mp4 -vf "scale=320:-1,split[s0][s1];[s0]palettegen[p];[s1][p]paletteuse" output.gif

```

## 2. Extract audio from video

You can also use FFmpeg to extract the audio from a video file and save it as a separate file. The command uses "-vn" to disable video recording and "-acodec" to specify the audio codec. Here is an example command:

```bash
ffmpeg -i input.mp4 -vn -acodec copy output.mp3

```

## 3. Merge multiple videos

FFmpeg can be used to merge multiple video files into a single file. The command uses the "concat" demuxer to concatenate the input files and the "-c copy" option to copy the video and audio streams without re-encoding. Here is an example command:

```bash
ffmpeg -i "concat:input1.mp4|input2.mp4" -c copy output.mp4

```

## 4. Convert video to audio

In addition to extracting audio, FFmpeg can also be used to convert a video file to an audio file. This command uses "-vn" to disable video recording and "-acodec" to specify the audio codec. Here is an example command:

```bash
ffmpeg -i input.mp4 -vn -acodec copy output.m4a

```

## 5. Change video resolution

FFmpeg can be used to change the resolution of a video file. The command uses the "scale" filter to resize the video to a width of 640 pixels and a height of 360 pixels. Here is an example command:

```bash
ffmpeg -i input.mp4 -vf scale=640:360 output.mp4

```

## 6. Add watermarks to videos

You can add a watermark to a video using ffmpeg. The `-i` option is used to specify the input video file and `-i` is used again to specify the watermark image. `overlay` filter is used to superimpose the watermark image on the video. The `main_w-overlay_w-10`,`main_h-overlay_h-10` arguments define the position of the watermark image. Here is an example command:

```bash
ffmpeg -i input.mp4 -i watermark.png -filter_complex "overlay=main_w-overlay_w-10:main_h-overlay_h-10" output.mp4

```

## 7. Add subtitles to videos

FFmpeg can be used to add subtitles to videos. The `-i` option is used to specify the input video file and the `-i` option is used again to specify the subtitle file. Here is an example command:

```bash
ffmpeg -i input.mp4 -i subtitle.srt -c:v copy -c:a copy -c:s mov_text output.mp4

```

## 8. Trim videos

You can use FFmpeg to trim a video by specifying the start and end times. The `-ss` option is used to specify the start time and the `-t` option is used to specify the duration. Here is an example command:

```bash
ffmpeg -i input.mp4 -ss 00:00:10 -t 00:00:20 -c:v copy -c:a copy output.mp4

```

## 9. Change video bitrate

FFmpeg can be used to change the bitrate of a video file. The `-b:v` option is used to specify the new video bitrate in bits per second. Here is an example command:

```bash
ffmpeg -i input.mp4 -b:v 500k output.mp4

```

## 10. Speed up or slow down videos

You can use FFmpeg to speed up or slow down a video. The `setpts` filter is used to adjust the playback speed. A value less than 1 slows down the video, while a value greater than 1 speeds up the video. Here is an example command to slow down a video by half:

```bash
ffmpeg -i input.mp4 -filter:v "setpts=2.0*PTS" output.mp4

```

These are just a few examples of the many tricks you can do with ffmpeg. With a little practice, you can use ffmpeg to accomplish almost any multimedia task you can imagine.

### Conclusion

FFmpeg is a powerful tool that can help you to manipulate multimedia files in a variety of ways. Whether you need to convert a video file to an audio file, add watermarks or subtitles to a video, or modify the resolution or bitrate of a video file, FFmpeg has you covered. By learning the tricks and commands of FFmpeg, you can save time and effort while enhancing your multimedia projects.
