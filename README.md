# Adaptive-Thresholding-to-Binarize-Degraded-Documents-with-Sauvola-Method-using-Integral-Images

This repo contains a local adaptive thresholding technique to binarize degraded documents using a modified version of Sauvola Method with the use Integral Images. We took inspiration from the paper: https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.182.5334&rep=rep1&type=pdf where it's shown how Sauvola method can be made almost as much efficient as Otsu Binarization  independent of the window size without having any impact on the method's quality.

### Sauvola Method:

This method has been proposed by Sauvola et al. in 1997 [8]. This approach is
actually inherited from Niblack method. It can successfully overcome the black noise
problem. The thresholding formula is as following:-
ܶ![image](https://user-images.githubusercontent.com/25950715/118011211-33630f00-b369-11eb-80a7-45482d9fb15e.png)
where k is a control factor in the range of [0.2, 0.5], R is a predetermined image graylevel value. The author suggested k=0.2, R= 125.


We have gathered some sample degraded images in the Original folder and performed both otsu and our method and saved outputs in respective folders.
