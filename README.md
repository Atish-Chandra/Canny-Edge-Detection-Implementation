# Canny-Edge-Detection-Implementation
The test image can be picked from Berkeley Segmentation Dataset. Link - https://www2.eecs.berkeley.edu/Research/Projects/CS/vision/bsds/
I will first smooth the images, then compute gradients, magnitude, and orientation of the gradient. This procedure is followed by non-max suppression, and finally hysteresis thresholding is applied to finalize the steps. 

The steps below for practical implementation of Canny Edge detector:
1. Read a gray scale image that can be find from Berkeley Segmentation Dataset, Training images, store it as a matrix named I.
2. Create a one-dimensional Gaussian mask G to convolve with I. The standard deviation(s) of this Gaussian is a parameter to the edge detector (call it σ > 0).
3. Create a one-dimensional mask for the first derivative of the Gaussian in the x and y directions; call these Gx andGy. Thesameσ>0valueisusedasinstep2.
4. Convolve Ix with Gx to give Ix′ , the x component of I convolved with the derivative of the Gaussian, and convolve Iy with Gy to give Iy′ , y component of I convolved with the derivative of the Gaussian.
5. Compute the magnitude of the edge response by combining the x and y components. The magnitude of the result can be computed at each pixel (x, y) as: M(x, y) = qIx′ (x, y)2 + Iy′ (x, y)2.
6. Implement non-maximum suppression algorithm. Pixels that are not local maxima should be removed with this method. In other words, not all the pixels indicating strong magnitude are edges in fact. There is need to remove false-positive edge locations from the image.
7. Apply Hysteresis thresholding to obtain final edge-map. 
