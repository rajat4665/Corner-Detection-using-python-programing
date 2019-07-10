# Corner-Detection-using-python-programing
In this Repository I am gonna show you practical implementation of  Harris corner detection with Open-CV using python programming.

<h3>A pipeline of Corner Detection using Harris corner with OpenCV.</h3>
<img class="alignnone size-full wp-image-128" src="https://getpython.files.wordpress.com/2019/07/harris_detector_pipeline.png" alt="Harris_detector_pipeline" width="742" height="196" />
<h3></h3>
<h3>How to run this code:</h3>
<ul>
	<li>download this code from my <a href="https://github.com/rajat4665/Corner-Detection-using-python-programing" target="_blank" rel="noopener">GitHub</a></li>
	<li>clone this repository</li>
	<li>open it into Jupyter notebook</li>
	<li>Now run its cells one by one</li>
</ul>
<h3>How to install jupyter notebook in Ubuntu:</h3>
open your terminal and paste these commands one by one.
<pre class="code-pre command"><code>sudo apt install python3-pip python3-dev</code></pre>
<pre class="code-pre command"><code>pip install jupyter</code></pre>
<h3>How to install jupyter notebook in windows:</h3>
Follow this <a href="https://jupyter-notebook-beginner-guide.readthedocs.io/en/latest/install.html">Link for windows</a>
<h3>Install these Requirements:</h3>
<pre>pip install OpenCV-python

pip install matplotlib

pip install numpy</pre>
<h3></h3>
<h3>Introduction:</h3>
Hello friends, welcome back to my another repository on Computer Vision. Have you guys ever thought how a machine see image or video?

Basically, image is a set of numerical data in which each pixel has a value from 0 to 255 according to color space. If I am talking about a color image which is consist of three channels (Red, Green, Blue), Here three sheets of RGB placed in a single stack whereas if we talk about grayscale images which consist of a single channel where the value of pixels varies from 0 to 255 in which 0 means black and 255 mean white.
<h3><b> Corner Detector:</b></h3>
There are many methods for corner detection but here I would like to talk about the Harris corner detector, later on, I will implement it in OpenCV.<b> Harris Corner Detector</b> is a corner detection operator that is commonly used in computer vision algorithms to extract corners and infer features of an image. It was first introduced by Chris Harris and Mike Stephens in 1988 upon the improvement of Moravec's corner detector. It is being used from many decades in the world of computer vision to detect corners from an image due to good accuracy and it is easy to implement.
<h3>Step0:</h3>
Import required modules
<pre>import matplotlib.pyplot as plt
import numpy as np
import cv2</pre>
<h3>Step1:</h3>
Read image using OpenCV
<pre>image = cv2.imread('Name_of_image.jpg')</pre>
<h3>Step2:</h3>
Convert image into RGB from BGR because OpenCV read an image in BGR format by default
<pre>image = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)</pre>
<h3>Step3:</h3>
Convert this image into grayscale because we need RGB channel for corner detection, Moreover, It reduces the size of information in the image and it helps to make the process fast.
<pre>gray = cv2.cvtColor(image, cv2.COLOR_RGB2GRAY)</pre>
<h3>Step4:</h3>
In this step, I implement the Harris corner detector to our grayscale image but first, we need to convert image information in float type for better accuracy.
<pre>gray = np.float32(gray)</pre>
<pre>dst = cv2.cornerHarris(gray, 2, 3, 0.04)</pre>
Here  2 represents the size of pixels to loop corners, 3 represents the size of kernel and 0.04 is the threshold.
<h3>Step5:</h3>
Apply dilation function which is morphological operation to enhance corner visibility in this case.
<pre>dst = cv2.dilate(dst,None)</pre>
<h3>Step6:</h3>
Now dst have coordinate information of  corners and we need to plot it on our original image
<pre># Define your thresh hold (thresh value <b>inversely proportional </b>to corner visbility )
thresh = 0.01*dst.max()

# Create copy of rgb image to draw corners on it.
corner_image = np.copy(image)

# Iterate through all the corners and draw them on the image 
for j in range(0, dst.shape[0]):
    for i in range(0, dst.shape[1]):
        if(dst[j,i] > thresh):
            # image, center pt, radius, color, thickness
            cv2.circle( corner_image, (i, j), 1, (0,0,255), 1)

plt.imshow(corner_image)</pre>
<h3>Step7:</h3>
Now time to save the final image in our local directory, here I am using matplotlib to save image.
<pre>plt.imsave("_cornerDetected_image.jpg",corner_image)

</pre>
Thank you for reading this article, Stay tuned for more articles.
