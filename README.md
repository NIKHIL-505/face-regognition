# face-regognition
using lbph algorithm and open cv a simple face recognition project is created



OPEN CV 
OpenCV-Python is a library of Python bindings designed to solve computer vision problems. ... All the OpenCV array structures are converted to and from Numpy arrays. This also makes it easier to integrate with other libraries that use Numpy such as SciPy and Matplotlib.

HAAR CASCADE
A Haar Cascade is a classifier which is used to detect the object for which it has been trained for. The Haar cascade is trained by superimposing the positive image over a set of images. This type of training is generally done on a server and on various stages. Better results are obtained by using high quality images and increasing the amount of stages for which the classifier is trained for. 
The algorithm can be explained in four stages:
Calculating Haar Features
Creating Integral Images
Using Adaboost
Implementing Cascading Classifiers

LBPH
The Local Binary Pattern Histogram(LBPH) algorithm is a simple solution on face recognition problem, which can recognize both front face and side face. However, the recognition rate of LBPH algorithm under the conditions of illumination diversification, expression variation and attitude deflection is decreased. To solve this problem, a modified LBPH algorithm based on pixel neighborhood gray median(MLBPH) is proposed. The gray value of the pixel is replaced by the median value of its neighborhood sampling value, and then the feature value is extracted by the sub blocks and the statistical histogram is established to form the MLBPH feature dictionary, which is used to recognize the human face identity compared with test image. 
COMING TO PROJECT 
 Data Collection
The first and the major part is to collect samples of data on which this model needs to be trained.
Defining Path 
Face Extraction : In this we basically convert the color of the captured images to gray because for many applications based on image processing, color information doesn’t help us identify important edges or other features. 
Multi Scaling : After the color transition we use detectMultiScale(), this basically detects objects of different sizes in the input image and the detected objects are returned as list of rectangle
Cropping Image : this is the very crucial part as in this we just crop the image so that we could get the face of the object.
Reading : Now after cropping the face we start reading. One thing that you must have noticed is that I used two variables to unpack the read function.
Resizing and saving the Output : The resize function here resizes the cropped image into the desired set of frames, also declaring the location of the file where the training data is going to be saved (“cv2.putText” is used to add text on the screen along with the video and “cv2.FONT_HERSHEY_COMPLEX” is the name of the font used just like Arial etc)


NOW THE SECOND MAIN PART
Training :
In this part we will train the model on the data that we have collected and based on the training our model will predict (based on confidence), whether the user is the same user or its somebody else
Before beginning the training we first need to get the data from the output file and then convert it into grayscale. After this color transition we then append the data into train_data.
Predicting :
This is the last and final step. In this we use test our model and calculate the confidence and based on this confidence we our model will determine and predict whether the user is the same for which the data has been trained or not. Few steps of this part are similar to the steps listed in part one(Defining path, Face Extraction, Multi scaling and Resizing). The only thing which is different is calculating confidence. First we set a threshold value, if our model predicts and the prediction value comes out to be less than the threshold value then only the confidence is calculated and If the value of confidence turns out to be greater than 80 then only the message “UNLOCKED” will pop otherwise the device will remain locked for every other faces.
