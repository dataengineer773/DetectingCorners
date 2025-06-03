We want to detect the corners in an image, Use OpenCV’s implementation of the Harris corner detector, cornerHarris, The Harris corner detector is a commonly used method of detecting the intersection of two edges. Our
interest in detecting corners is motivated by the same reason as for deleting edges: corners are points of
high information. A complete explanation of the Harris corner detector is available in the external
resources at the end of this recipe, but a simplified explanation is that it looks for windows (also called
neighborhoods or patches) where small movements of the window (imagine shaking the window)
creates big changes in the contents of the pixels inside the window. cornerHarris contains three
important parameters that we can use to control the edges detected. First, block_size is the size of the
neighbor around each pixel used for corner detection. Second, aperture is the size of the Sobel kernel
used (don’t worry if you don’t know what that is), and finally there is a free parameter where larger
values correspond to identifying softer corners.
The output is a grayscale image depicting potential corners, We then apply thresholding to keep only the most likely corners. Alternatively, we can use a similar
detector, the Shi-Tomasi corner detector, which works in a similar way to the Harris detector
(goodFeaturesToTrack) to identify a fixed number of strong corners. goodFeaturesToTrack takes
three major parameters—the number of corners to detect, the minimum quality of the corner (0 to 1),
and the minimum Euclidean distance between corners, 
