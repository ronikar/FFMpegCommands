# FFMpegCommands

## Get Video\Audio File Information

`ffmpeg -i video.mp4`

## Get Video Resolution 
Use FFprob

* defualt - `ffprobe -v error -select_streams v:0 -show_entries stream=width,height -of default=nw=1 input.mp4`
* csv - `ffprobe -v error -select_streams v:0 -show_entries stream=width,height -of csv=p=0 input.mp4`
* json - `ffprobe -v error -select_streams v:0 -show_entries stream=width,height -of json input.mp4`

## Concatenating Media Files
* Create a file `mylist.txt` with all the files you want to have concatenated
```
file '/path/to/file1.mp4'
file '/path/to/file2.mp4' 
file '/path/to/file3.mp4'
```
* Run - `ffmpeg -f concat -safe 0 -i mylist.txt -c copy output.mp4`
