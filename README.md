# Adaptive-Thresholding-to-Binarize-Degraded-Documents-with-Sauvola-Method-using-Integral-Images

This repo contains a local adaptive thresholding technique to binarize degraded documents using a modified version of Sauvola Method with the use Integral Images. We took inspiration from the paper: https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.182.5334&rep=rep1&type=pdf where it's shown how Sauvola method can be made almost as much efficient as Otsu Binarization, independent of the window size and without having any impact on the method's quality.

### Sauvola Method:

This method has been proposed by Sauvola et al. in 1997. This approach is
actually inherited from Niblack method. It can successfully overcome the black noise
problem. The thresholding formula is as following:-

ܶ![image](https://user-images.githubusercontent.com/25950715/118011211-33630f00-b369-11eb-80a7-45482d9fb15e.png)

where k is a control factor in the range of [0.2, 0.5], R is a predetermined image graylevel value. The author suggested k=0.2, R= 125. We can change value of k and R along with the window size in our code to achieve desired results.


### Integreal Images:

Integral image of any greyscale image can be efficiently computed in a single pass and in a single line of code with OpenCV .Once we have the integral image, the local mean m(x, y) for any window size can be computed simply by using two addition and two subtraction operations instead of the summation over all pixel values within that window:

![image](https://user-images.githubusercontent.com/25950715/118011850-e16eb900-b369-11eb-9fd4-19953eebb4b3.png)


Similarly, if we consider the computation of the local variance

![image](https://user-images.githubusercontent.com/25950715/118011874-ea5f8a80-b369-11eb-91af-f3af05d41120.png)

Substituting these mean and standard deviation values in the original sauvola method formula gives the same result as summing over all pixels values within a window but its many times faster. This helped us achieve the desired result with efficient runtime.


### About the Code:
We have gathered some sample degraded images in the Original folder and performed both otsu and our method and saved outputs in their respective folders. You can run **main.py** file which runs over the entire Original image folder to reproduce results. Our notebook file runs the method on a single example to compare Our results with Otsu method using image visualisaiton, you can try it yourself for other images. Feel free to try it on your own images and change values of R,k and window according to your needs.
