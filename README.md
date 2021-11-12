# mpv-video-cutter-linux

## This is a fork of https://github.com/rushmj/mpv-video-cutter

## Features

1. Patch to work with multiple video segments/cuts. Thanks  [@gabin22](https://github.com/gabin22)

2. OSD message for enhancements.  OSD displays messages! Thanks [@rushmj](https://github.com/rushmj) 

3. Flatpak support (with default directory to ~/Videos/mpv-cut/)  thanks to yours truly :-)

## How to Install

### For regular MPV users (distro based mpv)

Simply copy the 2 files `cutter.lua` and `c_concat.sh` in `mpv-video-cutter-linux`directory to `~/.config/mpv/scripts/` directory 

```
cd /tmp
git clone https://github.com/fastrizwaan/mpv-video-cutter-linux.git
mkdir -p ~/.config/mpv/scripts
cp mpv-video-cutter-linux/mpv-video-cutter-linux/* ~/.config/mpv/scripts
```

## For Flatpak Users of (io.mpv.Mpv) at flathub

```
cd /tmp
git clone https://github.com/fastrizwaan/mpv-video-cutter-linux.git
mkdir -p ~/.var/app/io.mpv.Mpv/config/mpv/scripts/
cp mpv-video-cutter-linux/flatpak/* ~/.var/app/io.mpv.Mpv/config/mpv/scripts/
```

Before using it,mpv and ffmpeg should be installed.support mac os x and linux,if you want it supports windows,you can write CMD instead of Bash Shell.  

   it can cut video and concat automatically  
put **c_concat.sh** , **cutter.lua** into ~/.config/mpv/scripts/,then use shell:mpv path/file open the movie
press c will confirm a left trim,then press c you will confirm a right trim,left and right trim ensure one segment,you can continue do this,at last press key o,the video will be cut and concatenated in the video's dir automatically.
this script uses the FFmpeg to finish the job,and is lossless cutting,the cut video will not lose quality. 

* **press key c** : cut point,the odd times is letf trim, the even times is right trim
* **press key o** : output the cut video and concat
* **press i** : output the accurate time cut video and concat
* **press key r** : reset,clean the queue that record the cut point
* **press s** : reset,and set the first cut point(left trim) in 0 second.
* **press e** : set the right trim in the end time of the video
* **press z** : undo the cut

also you can bind your own hot key to the event.
I have defined some event you can bind it in the ~/.config/mpv/input.conf,for example:Ctrl+s script-binding set_fromStart
here are them:

* **cut_movie** : cut time point,default key 'c'
* **log_time_queue** : print the queue that record the cut point,defalut key 'l'
* **output_queue** : output video,default key 'o'
* **set_fromStart** : reset,and set the first cut point(left trim) in 0 second,default key 's' 
* **set_End** : set the right trim in the end time of the video,default key 'e'
* **acu_output_queue** : accurate time cut 
* **undo** : undo

In fact,I should also add some more function like GUI editor?
