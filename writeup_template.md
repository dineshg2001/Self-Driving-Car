#**Finding Lane Lines on the Road** 

##Writeup Template

###You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

###1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 6 steps. 

1. Convert the image to grayscale
2. Apply canny and gaussian_blur functions on the image
3. I masked the image for required vertices
4. On the masked image I applied the HoughLinesP function to draw hough lines
5. I used draw_lines function to draw the lines completly
6. Then I combined the line image with the original image



In order to draw a single line on the left and right lanes, I modified the draw_lines() function by finding out teh slope of the lines and classifying them as left and right lines. I considered only lines with slope more than .5 to filter the unwanted lines. Then I applied linear reqgression to find out best fit line. 

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


###2. Identify potential shortcomings with your current pipeline
 

One potential shortcoming would be what would happen when the lines are little curved the aloritham is not able to identify the lanes properly 

Another shortcoming could be when the video is having countinus curved road the algoritham is not able to figure out the lanes at all. 


###3. Suggest possible improvements to your pipeline

A possible improvement would be to improve it to work on little curves by adjusting the way it works on slopes 

Another potential improvement could be to make it work on continus curved lanes. 