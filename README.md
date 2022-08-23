# Face-recogination-based-attendence-system

This system consist of 4 phase:
1. Dataset Creation
2. Face Detection 
3. Face Recogination
4. Attendence Updation
![WhatsApp Image 2022-08-23 at 9 17 08 AM (1)](https://user-images.githubusercontent.com/75435144/186091137-bec6bb13-8afa-438a-8dd2-f9db2bd708c2.jpeg)
![WhatsApp Image 2022-08-23 at 9 17 08 AM](https://user-images.githubusercontent.com/75435144/186091143-a1879e3c-d95b-4378-94bc-df6b9fee03cb.jpeg)





# Dataset Creation
Images of students are captured using a web cam. Multiple images of single student will be acquired with varied gestures and  angles.  These  images  undergo  pre-processing.  The images  are cropped  to obtain  the  Region of  Interest (ROI) which will be further used in recognition process. Next step is to resize the cropped images to particular pixel position. Then these  images  will  be  converted  from  RGB  to  gray  scale images. And then these images will be saved as the names of respective student in a folder.

# Face Detection
Face  detection  here  is  performed  using  Haar-Cascade Classifier with OpenCV. Haar Cascade algorithm needs to be trained to detect human faces before it can be used for  face detection. This is called feature extraction. The haar cascade training  data  used  is  an  xml  file- haarcascade_frontalface_default. Here we are using detectMultiScale module from OpenCV. This is required to create a rectangle around  the faces  in an image. It has got three  parameters to  consider-  scaleFactor, minNeighbors, minSize. scaleFactor  is used to indicate how much  an  image  must  be  reduced  in  each  image  scale. minNeighbors specifies how many neighbors each candidate rectangle must have. Higher values usually detects less faces but  detects  high  quality  in  image.  minSize  specifies  the minimum  object  size. 

# Face Recogination
Face recognition process can  be divided  into three steps- prepare training  data, train face recognizer, prediction.  Here training data will  be the images  present in the dataset. They will be assigned with a integer label of the student it belongs to.  These  images  are  then  used  for  face  recognition.  Face recognizer  used  in  this  system  is  Local  Binary  Pattern Histogram. Initially, the list of local binary patterns (LBP) of entire  face  is  obtained.  These  LBPs  are  converted  into decimal  number  and  then  histograms  of  all  those  decimal values are made.  At the end, one  histogram will  be formed for each images in the training data. Later, during recognition process histogram  of the  face to be recognized is calculated and then compared with the already computed histograms and returns the  best matched label associated with the student  it belongs to.

# Attendence Updation
After face recognition process, the recognized faces will be marked  as  present  in  the  excel  sheet  and  the  rest  will  be marked as absent  and the list of absentees will be mailed to the  respective  faculties.  Faculties  will  be  updated  with monthly attendance sheet at the end of every month.

