# **Finding Lane Lines on the Road** 



[//]: # (Image References)

[image1]: ./test_images_output/draw_line_0.png "Grayscale"

---

### Reflection

### 1. Description of pipeline.

My pipeline consisted of 5 steps. 
1. Blur the gray scale image
2. Apply canny edge
3. Apply mask region
4. Convert to binary image
5. Hough transform
6. Combine the image
![alt text][image1]

My draw_lines() function:
First I used the slope of the lines to separate left line and right line.
Then I selected the longest line in each side.
After that, I calculated the b value of the normal line function(y = kx + b) and used the function to locate the point that the line will intersect with the bottom of the image. By doing this, my lines will always start from the bottom of the image, even if the line in the image are dotted.
Finally, draw the lines on the image.


### 2. Potential shortcomings

If the line was curved, it might not work well.
If the line was not clear, or the weather was bad, the line might not be located.


### 3. Suggest possible improvements 

Find a better way to improve draw_lines() function
Find out how to dealing with curved line.
