# FFmpeg Multimedai Tool

#### Real life Examples :
 No | Explanation                                                         |
|---|---------------------------------------------------------------------|
| 1 | [**Converting bunch of mp4 videos in same folder using ffmpeg**](https://github.com/prakash-sparrow/FFmpeg/blob/main/FFmpeg.md#1-converting-bunch-of-mp4-videos-in-same-folder-using-ffmpeg)
| 2 | [**Merging All videos in One Video file**](https://github.com/prakash-sparrow/FFmpeg/blob/main/FFmpeg.md#2--merging-all-videos-in-one-video-file)
| 3 | [**Creating a Beep sound with FFmpeg**](https://github.com/prakash-sparrow/FFmpeg/blob/main/FFmpeg.md#3-creating-a-beep-sound-with-ffmpeg)
| 4 | [**Color Image to Black and White using FFmpeg**]()

---

## 1. Converting bunch of mp4 Videos in same folder using FFmpeg

&nbsp;<br>
Recurservely Convert all videos in current directory
```bash
for /r %a in (*.mp4) do ffmpeg -i "%a" -c:v libx265 -crf 30 "%a_converted_x265.mp4"
```
&nbsp;<br>


## 2 . Merging All videos in One Video file

&nbsp;<br>
This line prepare the all videos names in one file
```bash
(for %i in (*.mp4) do @echo file '%i')> mylist.txt
```
It start to convert the all video in one video file using the above text file
```bash
ffmpeg -f concat -safe 0 -i "mylist.txt" -c copy ouput.mp4
```
&nbsp;<br>


## 3. Creating a Beep sound with FFmpeg

&nbsp;<br>
This command will create a beep sound duration of 4 seconds
```bash
ffmpeg -f lavfi -i "sine=frequency=1000:sample_rate=48000:duration=4" -af apad -t 4 beep-sound.wav
```
&nbsp;<br>

## 4. Color Image to Black and White using FFmpeg
&nbsp;<br>
Images to Gray or black and white
```bash
ffmpeg -i input.png -pix_fmt gray output.png
```


