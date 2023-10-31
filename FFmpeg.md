# FFmpeg Multimedai Tool

#### Real life Examples :
 No | Explanation                                                         |
|---|---------------------------------------------------------------------|
| 1 |  Converting bunch of mp4 videos in same folder using ffmpeg
| 2 | 


##### 1. Converting bunch of mp4 videos in same folder using ffmpeg
`
for /r %a in (*.mp4) do ffmpeg -i "%a" -c:v libx265 -crf 30 "%a_converted_x265.mp4"
`
---
