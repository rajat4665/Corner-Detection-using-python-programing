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
