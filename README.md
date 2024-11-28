# AI Basketball Carrying Violation Detector

## 🎥 Demo Video
[![Youtube Video Demo](https://img.youtube.com/vi/mvQu2lTTaBc/0.jpg)](https://www.youtube.com/watch?v=mvQu2lTTaBc)

## 🏀 The Problem
Carrying is a basketball violation where a player decides to carry the ball in between dribbling actions. 

What makes this violation problematic is how fast-paced it is for even NBA referees to miss it oftentimes during live games. 

You can see tons and tons of videos on YouTube showcasing different NBA players violating this rule (yikes!). Below is an example.

[![Youtube Video Demo](https://img.youtube.com/vi/ZuFaQ6vVEKc/0.jpg)](https://www.youtube.com/watch?v=ZuFaQ6vVEKc)

Let me be clear. I’m not saying that players are bad or that referees aren’t doing their jobs. 

Carrying violations are often **unintentional** from players (fingers crossed 🤞), and referees missing them is completely understandable given the **fast-paced nature** of basketball. 

Even the best referees in the world can’t catch everything happening in real-time, because, let’s face it, they’re **only human**.

## The Role of AI
This is where the idea of using AI comes into play, **not as a replacement for referees**, but as a tool to assist them in detecting these quick, hard-to-spot violations!

Interestingly, a similar case study has already been done! Someone else built an AI-based basketball violation detector, but their project focused on **traveling violations**, while mine focuses specifically on **carrying violations**.

Shoutout to [@ayushpai](https://github.com/ayushpai) for their incredible work—it was a big inspiration for my project! 

If you’re curious, you can check out their GitHub repository here: https://github.com/ayushpai/AI-Basketball-Referee

## ⚙️ How It Works

The AI I used is a computer vision object detection model called YOLOv8. This model can detect the spatial information of the basketball throughout the video, tracking its position frame by frame. Below is an example.

[![Youtube Video Demo](https://img.youtube.com/vi/q8VdbdIyqE0/0.jpg)](https://www.youtube.com/watch?v=q8VdbdIyqE0)

However, detecting where the basketball is is only the first step. To accurately identify a carrying violation, the algorithm needs to understand the **difference between carrying and dribbling actions**. 

According to the basketball rulebook, a carrying violation involves a specific sequence of actions that distinguishes it from regular dribbling.

![Alt text for the image](ai-basketball-carrying-violation-detector/blob/main/images/sequence_of_actions.png)




