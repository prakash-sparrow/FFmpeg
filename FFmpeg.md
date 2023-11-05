# FFmpeg Multimedai Tool

#### Real life Examples :
 No | Explanation                                                         |
|---|---------------------------------------------------------------------|
| 1 | [**Converting bunch of mp4 videos in same folder using ffmpeg**](https://github.com/prakash-sparrow/FFmpeg/blob/main/FFmpeg.md#1-converting-bunch-of-mp4-videos-in-same-folder-using-ffmpeg)
| 2 | [**Merging All videos in One Video file**](https://github.com/prakash-sparrow/FFmpeg/blob/main/FFmpeg.md#2--merging-all-videos-in-one-video-file)
| 3 | [**Creating a Beep sound with FFmpeg**](https://github.com/prakash-sparrow/FFmpeg/blob/main/FFmpeg.md#3-creating-a-beep-sound-with-ffmpeg)
| 4 | [**Color Image to Black and White using FFmpeg**](https://github.com/prakash-sparrow/FFmpeg/blob/main/FFmpeg.md#4-color-image-to-black-and-white-using-ffmpeg)
| 5 | [**Calculating the Total Duration of Video files**](https://github.com/prakash-sparrow/FFmpeg/blob/main/FFmpeg.md#5-calculating-the-total-duration-of-video-file)

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
&nbsp;<br>

## 5. Calculating the Total Duration of Video Files
&nbsp;<br>

### LINUX
This command will calculate the total duration of video files with extensions mp4, mkv, and webm in the current directory and display the result in hours, minutes, and seconds
```bash
for video_file in *.{mp4,mkv,webm}; do ffprobe -v error -show_entries format=duration -of default=noprint_wrappers=1:nokey=1 "$video_file"; done | cut -d "." -f1 | awk '{s+=$1} END {printf "%d hours %d minutes %d seconds\n", s/3600, (s%3600)/60, s%60}'
```
&nbsp;<br>


