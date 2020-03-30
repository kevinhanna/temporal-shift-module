# W251 - Fall Detection



### Docker

Requires `/data/` directory and expects contents to be in `w251fall` subdirectory.

**Expects that host has NVIDIA GPU & Cuda (tested using Version 10.1).  It runs `xhost +` which is needed for preprocessing only, this may cause an error on host not running X11.**

Run `docker_run.sh`


## Data

### Raw Video Files

Video files should be `avi` files.  Each file should have a single fall.  The files need to be be stored in `/data/w251fall/videos/Fall` for preprocessing.

### Preprocessing

The preprocessing is going to output frames from the videos in to `/data/w251fall/jpg` (this directory needs to exist).  The directory structure will mimick the above Raw structure, but each video file will have its own directory with the same name excluding the file extention.  Inside will be a sequence of jpg files `img_00001.jpg`.

The the script:  
**For some reason, after running this script the terminal will stop echoing (can't see what you're typing).  I just restart docker.**

`python tools/vid2img_w251Fall.py /data/w251fall/videos/ /data/w251fall/jpg/`


## Training

### Create train and validation sets

**TODO**

### Transfer learn on Fall data

Run `fall_train.sh`

Checkpoint ends up in ``


### Jupyter Lab

Run `jupyterlab_run.sh`
