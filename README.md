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
&nbsp;apt-get update  
&nbsp;apt-get install -y libopencv-dev  
&nbsp;apt-get install -y cuda  


### 2. Clone the Darknet repository
&nbsp;git clone https://github.com/AlexeyAB/darknet.git  
&nbsp;cd darknet  


### 3.Build the darknet
&nbsp;update the makefile with   
&nbsp;&nbsp;&nbsp;GPU=1  
&nbsp;&nbsp;&nbsp;CUDNN=1  
&nbsp;&nbsp;OPENCV=1  
&nbsp;Then run  
&nbsp;&nbsp;&nbsp;make  


### 4.Data Preparation
&nbsp;1.Organize your dataset in data/obj/ with proper YOLO annotations (.txt files).  
&nbsp;2.Update obj.data with:  
 &nbsp;&nbsp;&nbsp;classes= 3  
 &nbsp;&nbsp;&nbsp;train  = data/train.txt  
 &nbsp;&nbsp;&nbsp;valid  = data/test.txt  
 &nbsp;&nbsp;&nbsp;names = data/obj.names  
 &nbsp;&nbsp;&nbsp;backup = backup/  
&nbsp;3.Adjust class names in obj.names (e.g., mask, no_mask, incorrect_mask).  
&nbsp;4.Configure your y.cfg file with appropriate training parameters (batch, subdivisions, filters, etc.).  
&nbsp;5.wget https://github.com/AlexeyAB/darknet/releases/download/darknet_yolo_v3_optimal_weights/darknet53.conv.74  



### 5.Training the model
&nbsp;./darknet detector train <path_to_obj.data> <path_to_y.cfg> <path_to_darknet53.conv.74>  


### 6.Install requirements for running the detection script  
&nbsp;pip install opencv-python numpy



### 7.Inference
&nbsp;Run the python scripts based on the use case  
&nbsp;&nbsp;&nbsp;1.python face_detect_image.py  
&nbsp;&nbsp;&nbsp;2.python face_detect_vedio.py  


### 8.sample output
&nbsp;Included example images or screenshots showing detection results.  







