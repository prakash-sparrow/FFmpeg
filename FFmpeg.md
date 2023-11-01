# FFmpeg Multimedai Tool

#### Real life Examples :
 No | Explanation                                                         |
|---|---------------------------------------------------------------------|
| 1 | [**Converting bunch of mp4 videos in same folder using ffmpeg**](https://github.com/prakash-sparrow/FFmpeg/blob/main/FFmpeg.md#1-converting-bunch-of-mp4-videos-in-same-folder-using-ffmpeg)
| 2 | [**Merging All videos in One Video file**]()

---

### 1. Converting bunch of mp4 videos in same folder using ffmpeg

`for /r %a in (*.mp4) do ffmpeg -i "%a" -c:v libx265 -crf 30 "%a_converted_x265.mp4"`

---

### 2 . Merging All videos in One Video file


`(for %i in (*.mp4) do @echo file '%i')> mylist.txt`

This line prepare the all videos names in one file

`ffmpeg -f concat -safe 0 -i "mylist.txt" -c copy ouput.mp4`

It start to convert the all video in one video file using the above text file

---
