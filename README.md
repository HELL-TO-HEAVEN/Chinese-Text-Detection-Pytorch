
# Recognize-Chinese-Characters-on-Traffic-Signs

## YOLOv3
### Requirements

Python 3.7 or later with the following `pip3 install -U -r requirements.txt` packages:

- `numpy`
- `torch >= 1.0.0`
- `opencv-python`

### Training

Gtx 1080 ti 12G RAM * 1  

**Start Training:** Run `train.py` to begin training 

**Transfer Learning** Run 'train.py --resume' to start from pretrained weighta

**num of class** 
1. traffic sign detection : 3 classes 
2. Chinese text : 1 class

### Image Augmentation Detail
[Reference](https://medium.com/uruvideo/dataset-augmentation-with-random-homographies-a8f4b44830d4)

Aug.| Description
---|---
Translation | +/- 10% (vertical and horizontal)
Rotation | +/- 5 degrees
Shear | +/- 2 degrees (vertical and horizontal)
Scale | +/- 10%
Reflection | 50% probability (horizontal-only)
HSV Saturation | +/- 50%
HSV Intensity | +/- 50%
Distortation | +/- 30%

### Inference

Please put test images into 
`yolov3/data/samples`
result will appear in `output/`
Run `detect.py` to apply trained weights to an image

### Performance

Run `test.py` to validate 

1. Red-Round Traffic Sign Detection
*127 epoches*
![](test_result.jpg?raw=true)

2. Text Detection
*50 epoch*
training details : 

num of epoch | resolution 
---|---
1-15 | 416x416
16-35 | 608x608
36-50 | 608-960(multi-scale)

![](result.jpg?raw=true)
(resume from 100 epoches)

