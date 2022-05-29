# Face_Recognition_Attendance_System_

A simple python script that recognises faces and mark attendance for the recognised faces in an excel sheet. You need following libraries pre-installed on your system: 
1. face-recognition 1.3.0 
2. opencv-python 4.5.5.64 
3. cmake 3.22.4 
4. datetime

HOW TO USE:

Save images of people in ImagesAttendance folderas 'name1.jpg','name2.jpg'...... name1, name2, ... being name of the person!

Run the program.

An excel file will be created, marked with the attendance for the faces it recognised.

Keep all the images and the python script in the same folder as well as run the python script for the same folder.

Excel will be created with the column as 'name' and 'time' of person marking attendance in  it.


## The Process of face Recognition can be divided into 3 steps.

# Step 1
Loading Images and Converting to RGB.
The Face Recognition package consists of a load image function that loads the image. Once imported the image has to be converted to RGB.
# Step 2
## Find Faces Locations and Encodings
In the second step we will use the true functionality of the face recognition library. First we will find the faces in our images . This is done using HOG (Histogram of Oriented Gradients) at the backend. Once we have the face they are warped to remove unwanted rotations. Then the image is feed to a pretrained neural network that out puts 128 measurements that are unique to that particular face. The parts that the model measures is not known as this is what the model learns by itself when it was trained. Lucky for us all this is done is just 2 lines of code. Once we have the face locations and the encodings we can draw rectangles around our faces.

# Step 3
## Compare Faces and Find Distance
Once we have the encodings for both faces, then we can compare these 128 measurements of these two faces to find similarities. To compare the package uses one of the most common machine Learning methods linear SVM classifier. We can use the compare_faces function to find if the faces match. This function returns True or False. Similarly we can use the face_distance function to find how likely is the faces match in terms of numbers. This is helpul particularly when there are multiple faces to detect from.

