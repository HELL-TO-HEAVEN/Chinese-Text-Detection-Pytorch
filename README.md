
# Recognize-Chinese-Characters-on-Traffic-Signs

## YOLOv3
### Requirements

Python 3.7 or later with the following `pip3 install -U -r requirements.txt` packages:

- `numpy`
- `torch >= 1.0.0`
- `opencv-python`

### Training

**Start Training:** Run `train.py` to begin training 
**Transfer Learning** Run 'train.py --resume' to start from pretrained weighta
**classes** 1. traffic sign detection : 3 classes
            2. Chinese 

### Image Augmentation Detail

Translation | +/- 10% (vertical and horizontal)
Rotation | +/- 5 degrees
Shear | +/- 2 degrees (vertical and horizontal)
Scale | +/- 10%
Reflection | 50% probability (horizontal-only)
H**S**V Saturation | +/- 50%
HS**V** Intensity | +/- 50%
Distortation | +/- 30%

### Inference
Please put test images into yolov3/data/samples,the result will appear in output/
Run `detect.py` to apply trained weights to an image

### Performance

Run `test.py` to validate 

#### Red-Round Traffic Sign Detection
67 epoches

