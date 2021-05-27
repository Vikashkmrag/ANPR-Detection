# ANPR-Detection
<img src="Output/car_460.jpg"
     alt="Result"
     style="float: center; margin-top: 10px;" />

## DataSet:
	Found that only one number plate is annotated in case image containing more than 1 number plate.
	Used Augmentation such as shear, flip, rotate, hsv to create five times data as given.

## Training:
	Used tensorflow object detection api to train model.

## Models:
	Used SSD-MobileNet-FPN for better accuracy than other mobilenet version and good fps as comparatively to bigger networks such as resnet etc.

## Result:
	Achieved around 0.90 mAP(0.5) in training data and 0.79 mAP(0.5) in val data.
	Inference time is around 100ms i.e. around >10fps in i5 processor
	Average FPS including Read/Processing/Inference/Write operation is around 10fps in i5 processor.

## More:
	Other smaller network can be tried if higher fps is needed such as SSDMobileNetV1,SSDMobileNetV2
	Model can be further quantised and converted to tflite for much faster inference, can also be used in raspberrypi.


## Steps:

    $ git clone https://github.com/Vikashkmrag/ANPR-Detection.git
    ---Input:  Input Images (34 images randomly taken fom validation set).
    ---Output:  Model output with bbox on them.
    ---ANPR-Detection.ipynb: Jupyter notebook for inference.
    ---InputAnnotations:  VOC Annotation to calculate mAP for each images.
    ---requirements.txt:   Required packages for inference
    ---label_map_licence.txt:   classes include in this file
    ---exported-model_ssd_fpn : Trained model dir

	$ pip3 install -r requirements.txt
	$ jupyter notebook
	-- Run all cells to get output
