# Tensorflow-based-object-detection-from-video-using-YOLO-Model
Object detection is a branch of computer vision, in which visually observable objects that are in images of videos can be detected, localized, and recognized by computers. An image is a single frame that captures a single-static instance of a naturally occurring event . On the other hand, a video contains many instances of static images displayed in one second, inducing the effect of viewing a naturally occurring event. Technically, a single static image in a video is called a video frame. In most videos, the number of frames in one second of the video ranges between 20 to 32, and this value is called the frames-per-second (fps).

In this project,  we’ll be using a Python library called ImageAI that has made it possible for anyone with basic knowledge of Python to build applications and systems that can detect objects in videos using only a few lines of programming code. ImageAI supports YOLOv3, which is the object detection algorithm we’ll use in this project.
To get started, you will install a number of Python libraries and ImageAI. If you have any of the dependencies mentioned below already installed on your computer, you can jump straight to the installation of ImageAI. Also ensure the Python version you have installed on 
your computer is Python 3.


pip3 install the following dependencies:
1) install TensorFlow using this command             
pip3 install tensorflow
2)  install  OpenCV                                  
pip3 install opencv-python
3)  install Keras                                 
pip3 install keras  
4)  install ImageAI library                         
pip3 install imageai --upgrade           

Now that we’ve installed the tools you need, we’ll be using a trained YOLOv3 computer vision model to perform the detection and recognition tasks. we used the pre trained YOLO model. the train Yolo model file is placed at my google drive link  https://drive.google.com/file/d/1K9_INogob2BYJ7RovJDBQH3Ma5OZh1pp/view?usp=sharing. so download that YOLO.h5 Model file from the given link and placed that file in same folder where python file and video file placed.  This model is trained to detect and recognize 80 different objects, named below:

classes {person, bicycle, car, motorcycle, airplane, bus, train, truck, boat, traffic light, fire hydrant, stop_sign, parking meter, bench, bird, cat, dog, horse, sheep, cow, elephant, bear, zebra,giraffe, backpack, umbrella, handbag, tie, suitcase, frisbee, skis, snowboard,sports ball, kite, baseball bat, baseball glove, skateboard, surfboard, tennis racket, bottle, wine glass, cup, fork, knife, spoon, bowl, banana, apple, sandwich, orange, broccoli, carrot, hot dog, pizza, donot, cake, chair, couch, potted plant, bed,dining table, toilet, tv, laptop, mouse, remote, keyboard, cell phone, microwave,oven, toaster, sink, refrigerator, book, clock, vase, scissors, teddy bear, hair dryer,toothbrush.}


Next, we create a Python file and give it a name, e.g FirstVideoDetection.py. Then we copy both the downloaded video and YOLOv3 model file into the folder where our FirstVideoDetection.py file is. Once you have done that, we write the exact code which contain our file firstvideodetection.py file. into our FirstVideoDetection.py file.


Before we run our Python code, here’s an in-depth explanation of the preceding code:
1) In the fourth line, we created an instance of the VideoObjectDetection class.
2) In the fifth line, we set the model type to YOLOv3, which corresponds to the YOLO model we downloaded and copied to the folder.
3) In the sixth line, we set the model path to the file path of the model file we copied into the folder.
4) In the seventh line, we loaded the model into the instance of the VideoObjectDetection class that we created.
5) In the eight line, we called the detectObjectsFromVideo function and parsed the following values into it:
i. input_file_path: This refers to the file path of the video we copied into the folder.
ii. output_file_path: This refers to the file path to which the detected video will be saved.
iii. frames_per_second: This refers to the number of image frames that we want the detected video to have within a second.
iv. log_progress: This is used to state that the detection instance should report the progress of the detection in the command line interface.
6) The detectObjectsFromVideo function will return the file path of the detected video. This file path will be printed in the ninth line of code once the detection task is done.


Once the detection is done, we’ll find the detected video in the folder that contains our Python file. When we open and play the video, it will contain the original video, but in this case, with boxes that locate various objects, the names of those objects, and the probability of the recognition as a percentage.
As of now, we’ve applied the trained YOLOv3 model to detect objects in a video file. We can use this code to detect and recognize objects in any other video file, apart from the one provided in this article.


Next, we’ll look at how to detect and recognize objects in camera feeds. The camera can be the default one pre-installed on our computer system, a camera connected by cable, or an IP Camera. To do this, we create another Python file in the folder where the YOLOv3 model is and give it a name, e.g FirstCameraDetection.py.
Once we’ve created the Python file, we copy the code below and write it into our new Python file. check the file in our folder in the same name.


The code above in the file firstcameradetection.py similar to our previous code. The differences are as stated below:
1) We created an instance of OpenCV’s VideoCapture class and loaded the computer’s camera into it.
3) Then in the detectObjectsFromVideo function, we stated the camera_input instead and parsed the name of the camera instance we created, unlike the input_file_path we used in the previous detection code.
These are the differences in detecting and recognizing objects in video files versus from camera feeds. Now, we can run the code and watch the progress in the command line interface.


If we’re planning to detect and recognize objects from the feeds of an IP Camera, all we need is to obtain the address of the IP Camera and load it with OpenCV, as seen in the example below:


camera = cv2.VideoCapture("http://192.168.43.1:8080/video")
