# Safety Helmet Detection Based on YOLOv5

This repo includes the Jupyter Notebook for the project of my Master's Artificial Intelligence class.

The Google Drive cloud platform is used to store the data set, annotations and labels. Google Colaboratory platform is used for experiments such as training and prediction. Colab is a hosted Jupyter notebook service that requires no setup to use, while providing free access to computing resources including GPUs.

## Dataset

A total of 5000 images with bounding box annotations in the PASCAL VOC [6] format were obtained for the scope of this study. Around 17500 helmets and 5500 head label
instance occurred in the images. Dataset is splitted into 3 categories; training, validation and test. There are 4000 images for training, 500 for validation and 500 for testing the model. The classes are:
• Helmet
• Head
• Person

## Training Results

Training is performed with 10 and 30 epochs, 32 batch, 416x416 image size, 0.001 learning rate, other training configurations is left as default from Yolo v5. Precision, recall
and mAP values are given in the table below.

| Algorithm | Epoch | Precision | Recall | mAP 0.5 | mAP 0.5:0.95 |
|-----------|-------|-----------|--------|---------|--------------|
| Yolov5n   | 30    | 0.665     | 0.711  | 0.713   | 0.432        |
| Yolov5s   | 10    | 0.958     | 0.589  | 0.659   | 0.413        |
| Yolov5s   | 30    | 0.897     | 0.782  | 0.848   | 0.535        |

Yolo v5s algorithm clearly more precise than Yolo v5n. As it can be seen from the table even though precision of the 10 epoch training is higher, recall and map values are lower
than the training with 30 epochs. So, for the detection and prediction of test images, it is more reasonable to use the weights of the second training. The main reason of why the
mAP 0.5:95 values are so low is the labeling of person class. Even though the values for helmet and head class are above 0.93 for both training’s person class performed poorly.
