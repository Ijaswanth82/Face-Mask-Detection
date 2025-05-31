# Face Mask Detection using YOLO and Darknet

This project performs face mask detection to identify whether people are wearing masks correctly using the YOLO (You Only Look Once) object detection model. The model is trained using the [Darknet](https://github.com/AlexeyAB/darknet) framework.

## 🚀 Features

- Detects whether a person is:
  - Wearing a mask correctly
  - Wearing a mask incorrectly
  - Not wearing a mask
- Real-time detection using webcam or images
- YOLO-based custom training using labeled dataset

---

## 🛠️ Setup & Training


### 1. Install dependencies
apt-get update
apt-get install -y libopencv-dev
apt-get install -y cuda


### 2. Clone the Darknet repository
git clone https://github.com/AlexeyAB/darknet.git
cd darknet


### 3.Build the darknet
update the makefile with 
GPU=1
CUDNN=1
OPENCV=1
Then run
make


### 4.Data Preparation
1.Organize your dataset in data/obj/ with proper YOLO annotations (.txt files).
2.Update obj.data with:
 classes= 3
 train  = data/train.txt
 valid  = data/test.txt
 names = data/obj.names
 backup = backup/
3.Adjust class names in obj.names (e.g., mask, no_mask, incorrect_mask).
4.Configure your y.cfg file with appropriate training parameters (batch, subdivisions, filters, etc.).
5.wget https://github.com/AlexeyAB/darknet/releases/download/darknet_yolo_v3_optimal_weights/darknet53.conv.74



### 5.Training the model
./darknet detector train <path_to_obj.data> <path_to_y.cfg> <path_to_darknet53.conv.74>


### 6.Install requirements for running the detection script
pip install opencv-python numpy



### 7.Inference
Run the python scripts based on the use case
1.python face_detect_image.py
2.python face_detect_vedio.py





