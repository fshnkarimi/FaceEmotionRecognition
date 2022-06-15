# Face Emotion Recognition

The Face Emotion Recognizer (generally knowns as the FER) is an open-source Python library built and maintained by [Justin Shenk](https://www.linkedin.com/in/justinshenk/?originalSubdomain=de) and is used for sentiment analysis of images and videos. The project is built on a version that uses a convolution neural network with weights mentioned in the HDF5 data file present in the [source code](https://github.com/justinshenk/fer/tree/master/src/fer/data) (The execution of FER can be found here) of this system’s creation model.

* 1- MTCNN (multi cascade convolutional network) is a parameter of the constructor. It is a technique to detect faces. When it is set to ‘True’ the MTCNN model is used to detect faces, and when it is set to ‘False’ the function uses the default OpenCV Haarcascade classifier.


* 2- detect_emotions(): This function is used to classify the detection of emotion and it registers the output into six categories, namely, ‘fear’, ‘neutral’, ‘happy’, ’sad’, ‘anger’, and ‘disgust’. Every emotion is calculated, and the output is put on a scale of 0 to 1.

**The flow of Logic:** The program starts by taking into input the image or video that needs analysis. The FER() constructor is initialized by giving it a face detection classifier (either Open CV Haarcascade or MTCNN). We then call this constructor’s detect emotions function by passing the input object (image or video) to it. The result achieved is an array of emotions with a value mentioned against each. Finally, the ‘top_emotion’ function can seclude the highest valued emotion of the object and return it.

* 1- Video_analyze(): This function is responsible for extracting the individual image frames from a video and then analyze those independently.
* 2- Each frame analyzed by this function is stored as a separate image by the algorithm in the root directory folder where the code is running. Also, this function later creates a replica of the original video by placing a box around the face and showing live emotions within the video.
* 3- We then create a Pandas DataFrame from these analyzed values and plot this dataframe using matplotlib. In this plot, we can see every emotion plotted against time.
* 4- We can further analyze this dataframe by taking individual emotion values that were recognized by the model and finding which sentiment was dominant across the entire video.

This way, we can work on videos by extracting individual image frames and analyzing them. This process is displayed in the diagram below that shows how an additional step gets added for processing videos. We will be seeing this implementation in the section below.

![diagram](https://miro.medium.com/max/700/1*sw5HvtLvXQJyGs8Ukh0iTQ.png)

**Output**

[emotionplot](https://user-images.githubusercontent.com/22480607/173799703-198e630e-d27b-46b6-bec9-6781fca8a3ae.png)

|index|Human Emotions|Emotion Value from the Video|
|---|---|---|
|0|Angry|35\.60000000000001|
|1|Disgust|2\.4899999999999993|
|2|Fear|23\.619999999999983|
|3|Happy|61\.319999999999986|
|4|Sad|27\.73999999999999|
|5|Surprise|1\.760000000000001|
|6|Neutral|120\.65999999999997|

[FER_Result](https://github.com/fshnkarimi/FaceEmotionRecognition/blob/main/Videos/FER_Output.gif?raw=true)

**Reference**

[The Ultimate Guide to Emotion Recognition from Facial Expressions using Python](https://towardsdatascience.com/the-ultimate-guide-to-emotion-recognition-from-facial-expressions-using-python-64e58d4324ff)
