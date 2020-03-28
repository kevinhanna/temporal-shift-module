# W251 - Fall Detection



### Docker

Requires `/data/` directory and expects contents to be in `w251fall` subdirectory. 

Run `docker_run.sh`

* Expects that host has GPU.  Also runs `xhost +` which is needed for preprocessing, this may cause an error on host not running X11.

## Data

### Raw Video Files

Video files should be `avi` files.  Each file should have a single fall.  The files need to be be stored in `/data/w251fall/videos/Fall` for preprocessing.

### Preprocessing

The preprocessing is going to output frames from the videos in to `/data/w251fall/jpg` (this directory needs to exist).  The directory structure will mimick the above Raw structure, but each video file will have its own directory with the same name excluding the file extention.  Inside will be a sequence of jpg files `img_00001.jpg`.

The the script:
`python tools/vid2img_w251Fall.py /data/w251fall/videos/ /data/w251fall/jpg/`


## Training

Run `fall_train.sh`

Checkpoint ends up in ``
