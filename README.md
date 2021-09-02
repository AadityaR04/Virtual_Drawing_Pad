# Virtual Drawing Pad

## A Briefing

This project on Virtual Drawing Pad is an OpenCV Implementation.
The two main processes involved during the implementations are:

1. Object Detection and Tracking
2. Drawing Program

## 1. Object detection and Tracking

In this part, we isolate from the background our stylus only which is a single tone object. To do that, we deploy the following methods:

* Finding the color of the stylus
* Finding the HSV values and hence setting the upper and lower limits of HSV
* Removing the noise from the frame using Gaussian Filtering.
* Thresholding the frame using the upper and lower values of HSV to get the object mask.
* The object mask undergoes `opening` and `dilation` to remove noise and extra contours and enhances the  object respectively.

Now with the stylus specifically isolated, we can now track it's positions as it changes it's place across the frame.

## 2. Drawing Program

The isolated object is tracked and using it, we use it as a pen to draw it on the screen. Since the object is a region and not a point, we have to reduce the region to a point.
To do this, the main processes are involved:

* Finding the Canny edge of the threshold mask and generating an edge image.
* Finding the Contours of the edge image.
* Using the contours, making a minimum enclosing circle around the edge image.
* Using the centre of this enclosing circle, we use it as the specific coordinates of the pen.

Now once we have the single coordinates of the pen, we can use it to draw the image on the Virtual Drawing Program.

---

🔗LINK TO THE VIDEO

https://drive.google.com/file/d/1IHus71NbExvZWdHzGw_C0oInf4oUoy2N/view?usp=sharing

---
