# Image stitching

<p align="center">
   <br>
   <img src="Images/1_Demonstration.jpg" width="70%" height="70%">
   <br>
</p>

# Harris corner detection
To have the images stitching together we need to find the corresponding point for each pair of images, although SIFT is a good choice capable to detect feature that is scale invariant, but here since the images are of similar scale and also because Harris method is faster to implement is the main reason we use Harris method.

**Corner feature** <br>
Here's the graph showing corner feature to be detected, in first glance we could observe that the pixel intensity at the point of corner changes instantly:

<p align="center">
   <br>
   <img src="Images/2_Corner_feature.jpg" width="70%" height="70%">
   <br>
</p>

**Gradient plot** <br>
If we calculate the first order derivative over the image, we could even observe the derivatives along plane, edges and corner are distributed in it's own way:

<p align="center">
   <br>
   <img src="Images/2_Corner_feature_gradient_plot.jpg" width="70%" height="70%">
   <br>
</p>

**Taylor series appriximation** <br>
From the taylor series approximation we could find that the matrix containing first order derivative is indeed determining how instant changes it is around each point:

<p align="center">
   <br>
   <img src="Images/3_Taylor_series_approximation.jpg" width="70%" height="70%">
   <br>
</p>

**Eigenvalues determine instant changes** <br>
The use of eigenvalues is better than derivatives in the sense that eigenvalue would determines the amount of changes and automatically aligns with the direction of greatest changes, so by analyzing the eigenvalue we could determine whether the current point is a plane, edge or corner:

<p align="center">
   <br>
   <img src="Images/4_Eigenvalues_determines_instant_changes.jpg" width="70%" height="70%">
   <br>
</p>

**Corner feature detected** <br>
Here's a example of the corner feature detected withiin the image:

<p align="center">
   <br>
   <img src="Images/5_Corner_feature_detected.jpg" width="70%" height="70%">
   <br>
</p>

# Gradient descriptor
Once the feature has been detected we'll need to describe it, to have the property of orientation invariant SIFT descriptor is using.

**Main orientation** <br>
To achieve orientation invariant the first step is to calculate the histogram of gradient, and find the main orientation of gradient for each point:

<p align="center">
   <br>
   <img src="Images/6_Gradient_8_orientation.jpg" width="50%" height="50%">
   <br>
</p>

**Histogram of gradient** <br>
And again calculate the histogram of gradient, this time the orientation is based on the main orientaion:

<p align="center">
   <br>
   <img src="Images/7_Histogram_of_gradient.jpg" width="70%" height="70%">
   <br>
</p>

**Flatten form** <br>
Once we've finished the calculation of histogram statistics, the next step is to flatten into a vector show in the following graph:

<p align="center">
   <br>
   <img src="Images/8_Flatten_form.jpg" width="70%" height="70%">
   <br>
</p>

# Feature matching
Here nearest neighbor is used to find the match point for each feature, and some filtering process is needed to provide more accurate result.

**Histogram of slope and length**
In this stage we'll get some potential matching point, the next step is to calculate the histogram for both the slope and length of matching point:

<p align="center">
   <br>
   <img src="Images/11_Histogram_of_slope_and_length.jpg" width="70%" height="70%">
   <br>
</p>

**Inlier detection**


<p align="center">
   <br>
   <img src="Images/12_Inlier.jpg" width="70%" height="70%">
   <br>
</p>

# 9_Cylindrical_mapping

<p align="center">
   <br>
   <img src="Images/9_Cylindrical_mapping.jpg" width="70%" height="70%">
   <br>
</p>

# 10_Cylindrical_mapping_with_real_scene

<p align="center">
   <br>
   <img src="Images/10_Cylindrical_mapping_with_real_scene.jpg" width="70%" height="70%">
   <br>
</p>

# 13_Linear_blending

<p align="center">
   <br>
   <img src="Images/13_Linear_blending.jpg" width="70%" height="70%">
   <br>
</p>

# 14_Final_result

<p align="center">
   <br>
   <img src="Images/1_Demonstration.jpg" width="70%" height="70%">
   <br>
</p>


