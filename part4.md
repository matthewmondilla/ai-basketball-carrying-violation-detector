# Data Cleaning
Cleaning real-world data is like doing laundry: necessary, occasionally tedious, but absolutely worth it. YOLOv8 gave me a good starting point, but as with any AI model, it wasn’t perfect. 


## Limitations of YOLO

While it’s excellent at detecting objects, it occasionally got creative. Sometimes, it decided my shoe was the basketball (yep). 

Other times, the basketball disappeared entirely if it moved too close to the edge of the frame. 

And let’s not forget the bounding box height inconsistencies caused by occlusion (by my hand and sometimes, my other hand). 

![Alt text for the image](images/limit.png)

## Whittaker-Eilers Smoothing Filter
To fix this, I brought in the **Whittaker-Eilers Smoothing Filter**. Now, I’m not going to bore you with all the math behind it (you’re welcome), but here’s why I used it: 

I stumbled upon this [resource](https://towardsdatascience.com/the-perfect-way-to-smooth-your-noisy-data-4f3fe6b44440) and thought, “Hey, this might work.” And it did! The filter not only smoothed out noisy data but also helped interpolate missing points when YOLO decided to take a coffee break.

It’s particularly useful because it allows you to adjust the smoothness to align with expected physical behaviors, like the constant acceleration due to gravity.

Still, smoothing alone wasn’t enough. The gaps in my data varied from small to large, so I implemented an **interpolation threshold**. This means that any missing sequence of data points longer than 24 frames was ignored, as they are too sparse to interpolate reliably. 

Similarly, small clusters of detected data points surrounded by large gaps were excluded because they didn’t provide enough context to interpolate reliably. By implementing the **interpolation threshold**, we can transform the noisy data as shown in the diagram below.

![Alt text for the image](images/limit.png)

