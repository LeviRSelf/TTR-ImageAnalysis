# TTR-ImageAnalysis
Performs a transformation on an image of a TTR board so it can be compared to a reference image.

This is part of a larger work developing a smartphone app which would allow users
to photograph a TTR game board for automatic scoring.

This code sample straightens and resizes the photo so it can be compared to a reference image.
To do this, a homography is needed which requires at least 4 matching points.

## Process:
1. The small orange city vertices are template matched to one of the citypoint_xx.jpg files
2. The matched points are used as keypoints and compared to the reference keypoints via K-Nearest Neighbors and SIFT
3. The first 4 correspondences (matches between city vertices in the input image and the reference) are used to compute a homography matrix
4. The transformation is used to reshape the input image to be like the reference and the output is saved in the ouput folder.
5. Additionally, the output image is overlaid with the city names of the 4 keypoints used in the homography, as well as green rectangles around where each train location is.

## Results:

[Input #1](photos/0523152031a.jpg) [Output #1](output/res_0523152031a.jpg.png)
[Input #2](photos/0523152125.jpg) [Output #2](output/res_0523152125.jpg.png)
[Input #3](photos/0526152249.jpg) [Output #3](output/res_0526152249.jpg.png)
