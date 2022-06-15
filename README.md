# Face Emotion Recognition

The Face Emotion Recognizer (generally knowns as the FER) is an open-source Python library built and maintained by [Justin Shenk](https://www.linkedin.com/in/justinshenk/?originalSubdomain=de) and is used for sentiment analysis of images and videos. The project is built on a version that uses a convolution neural network with weights mentioned in the HDF5 data file present in the [source code](https://github.com/justinshenk/fer/tree/master/src/fer/data) (The execution of FER can be found here) of this system’s creation model.

MTCNN (multi cascade convolutional network) is a parameter of the constructor. It is a technique to detect faces. When it is set to ‘True’ the MTCNN model is used to detect faces, and when it is set to ‘False’ the function uses the default OpenCV Haarcascade classifier.


detect_emotions(): This function is used to classify the detection of emotion and it registers the output into six categories, namely, ‘fear’, ‘neutral’, ‘happy’, ’sad’, ‘anger’, and ‘disgust’. Every emotion is calculated, and the output is put on a scale of 0 to 1.
