# Automatic Number plate Detection
Number plate recognition is one of the most crucial tasks which can benefit us in every way. It has already been widely adopted by many countries for surveillance purposes but in India where the size of the number plate is not fixed and most of the CCTV cameras are not of high resolution- ANPR remains a challenge to be solved. Automatic Number plate detection is very challenging as the detection of regions containing number plates and recognizing them varies from place to place. So, we have come up with a solution for it using YOLOv3 and Pytesseract.

# Dataset
This is one of the hardest part to work. Since there is no any standard indian ANPR dataset is available, I downloaded the the dataset from kaggle and had to annotate it manually. you can download the dataset from [here](https://www.kaggle.com/scholngusmaximus/numberplate-bounding-box-india-eu-brazil-us)

# YOLOv3 Architecture
![](https://github.com/chandan5362/Automatic-Number-plate-Detection---ANPR/blob/f3ccd92a110806a9e1a10997001d2ae782db720d/yolov3.JPG)

The YOLOv3 algorithm first divides an image into a grid. Each grid cell predicts some number of boundary boxes (sometimes referred to as anchor boxes) around objects that score highly with the aforementioned predefined classes. Each boundary box has a respective confidence score of how accurate it assumes that prediction should be, and detects only one object per bounding box. You can download the darknet pretrained model from [here](https://github.com/pjreddie/darknet)

# Character recognition
Pytesseract has been used for optical character recognition from the cropped Number plate . It can be installed using pip. <br>
```pip install pytesseract```

# Usage
### To detect the number plate and crop it, use the following command.
```python path/to/recognition.py -i path/to/test-image -c path/to.yolov3.cfg -w path/to/model -c path/to/obj.names```

### to recognize the number, use the following command
```python path/to/ocr.py -i path/to/cropped-image```
