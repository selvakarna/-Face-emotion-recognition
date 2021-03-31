# Emotion-detection

## Dependencies

* Python 3, [OpenCV 3 or 4](https://opencv.org/), [Tensorflow 1 or 2](https://www.tensorflow.org/)
* To install the required packages, run `pip install -r requirements.txt`.

## Usage

The repository is currently compatible with `tensorflow-2.0` and makes use of the Keras API using the `tensorflow.keras` library.

* First, clone the repository with `git clone https://github.com/atulapra/Emotion-detection.git` and enter the cloned folder: `cd Emotion-detection`.


* If you want to train this model or train after making changes to the model, use `python emotions.py --mode train`.


* The folder structure is of the form:  
  Tensorflow:
  * data (folder)
  * `emotions.py` (file)
  * `haarcascade_frontalface_default.xml` (file)
  * `model.h5` (file)

* This implementation by default detects emotions on all faces in the webcam feed.

* With a simple 4-layer CNN, the test accuracy peaked at around 50 epochs at an accuracy of 63.2%.

![Accuracy plot](accuracy.png)

## Algorithm

* First, we use **haar cascade** to detect faces in each frame of the webcam feed.

* The region of image containing the face is resized to **48x48** and is passed as input to the ConvNet.

* The network outputs a list of **softmax scores** for the seven classes.

* The emotion with maximum score is displayed on the screen.


