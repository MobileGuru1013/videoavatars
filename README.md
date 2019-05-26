# Video Avatars

This repository contains code corresponding to the paper **Video based reconstruction of 3D people models**.

## Installation

Download and unpack the SMPL model from here: http://smpl.is.tue.mpg.de/.

Download and unpack the SMPLify Code from here: http://smplify.is.tue.mpg.de/


```
git clone https://github.com/thmoa/videoavatars.git videoavatars
cd videoavatars/vendor
mkdir smpl
cd smpl
touch __init__.py
ln -s <path to smpl folder>/models .
ln -s <path to smpl folder>/smpl_webuser/*.py .
cd ..

mkdir smplify
cd smplify
touch __init__.py
ln -s <path to your smplify installation>/code/models .
# this file needs to be copied!
cp <path to your smplify installation>/code/lib/sphere_collisions.py .
# these files can be linked
ln -s <path to smplify folder>/code/lib/capsule_body.py .
ln -s <path to smplify folder>/code/lib/capsule_ch.py .
ln -s <path to smplify folder>/code/lib/robustifiers.py .
```

Change line 14 in `vendor/smplify/sphere_collisions.py` to
```
from vendor.smpl.lbs import verts_core
```

## Usage

The software consists of three parts:

1. `step1_pose.py`: pose reconstruction
2. `step2_consensus.py`: consensus shape optimization
3. `step3_texture.py`: texture calculation

Starting the scripts will display usage information and options.
Additionally, we provide helper bash scripts for easier processing of our dataset.

The scripts in `prepare_data` might help you to process your own data.

## Citation

Please cite as:

```
@inproceedings{alldieck2018video,
  title = {Video Based Reconstruction of 3D People Models},
  author = {Alldieck, Thiemo and Magnor, Marcus and Xu, Weipeng and Theobalt, Christian and Pons-Moll, Gerard},
  booktitle = {{IEEE} Conference on Computer Vision and Pattern Recognition},
  year = {2018}
}
```


## Dataset

The accompanied dataset can be downloaded here: https://graphics.tu-bs.de/people-snapshot


