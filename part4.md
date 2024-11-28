## Data Cleaning
In this section, I’ll address how I cleaned the position vs. time series data to handle limitations in detection and improve the accuracy of the results. 

Cleaning was essential to address noise, gaps, and inconsistencies in the raw data caused by real-world factors.

# Limitations of YOLO

While YOLOv8 is a powerful object detection model, it has certain limitations that introduced noise into the data. These include:

- Misclassification: Occasionally, my shoe was misclassified as the basketball.
- Partial Visibility: The basketball was undetected when partially outside the video frame.
- Bounding Box Inconsistencies: Occlusions caused fluctuating bounding box heights.

![Alt text for the image](images/limit.png)

# Whittaker-Eilers Smoothing Filter
To handle missing data and smooth noisy measurements, I used the Whittaker-Eilers Smoothing Filter. I won’t delve into the intricate details of this filter, 

but I chose it after coming across this [resource](https://towardsdatascience.com/the-perfect-way-to-smooth-your-noisy-data-4f3fe6b44440) and learning about its interpolation capabilities and its ability to control the smoothness in terms of its derivative.
