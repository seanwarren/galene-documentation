Correction Modes
==================================

There are three correction modes which are described below. In most cases, `Warp` correction is the most appropriate option.

Translation
-------------- 
In this mode, each frame is realigned to the reference frame taking a constant *x,y* translation into account.
This mode is appropriate when the sample motion is very slow relative to the frame rate so the distortion within a frame is negligible. 
This translation is used as an initial estimate by default for the Warp mode, so in general the Warp translation will provide a better result. 

Options
 - ``Spatial binning``: Spatially downsamples the data by this factor. 
   Increasing this value can improve the realignment of noisy data at the cost of some realignment precision.
 
 - ``Frame binning``: Bins multiple frames together. 
   Increasing this value can improve the realignment of noisy data when the motion over a number of frames is slow.

Warp
-------------- 
In this mode, the displacement at multiple points during each frame is estimated. This allows us to correct for motion faster than
the frame rate which cause distortions to the image. 

Frames which are not well aligned, for example if the sample moves out of the field of view, can degrade the final image. 
These frames can be rejected by applying thresholds to the realigned frames.

Options
 - ``Realignment Points``: controls the number of points in the image used to estimate the displacement 
   during each frame. We have found that the default value of 10 points provides good results across a range of images. 
   If the motion is fast relative to the frame you may need to use more points to accurately estimate the motion. 
   If the realignment appears 'jittery', try using fewer points. If the displacement during each frame is relatively small
   as few as 4 points may be sufficient.   
 - ``Smoothing``: controls the degree of smoothing in the x-axis applied to the image before realignment. Increasing the 
   degree of smoothing can improve the realignment when the signal to noise in each frame is low. 
 - ``Correlation Threshold``: applied to reject frames where the correlation with the reference frame is low.
 - ``Coverage Threshold``: applied to reject frames where the displacement was very large. 
