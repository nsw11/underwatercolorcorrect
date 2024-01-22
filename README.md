# underwatercolorcorrect
# Introduction
Recently I have become interested in underwater photography using an action cam, however as you get deeper in water, red light is filtered out of the image, giving the entire video a green/blue haze. Generally, color correction is done with photo editing software like Adobe Lightroom or Davinci, however these methods are slow and require a lot of personal time to achieve good results. The goal of this project is to create a OpenCV program that takes in a video and automatically color corrects it, working on each frame individually, in hopes of achieving better color correction results than I, an unskilled ameteur photographer and editor could achieve on my own.


# Initial Thoughts
## Initial Workflow
1. Find average value of the entire image
2. Figure out how to hueshift the values in the image to increase the amount of red in the image (until average red value is like 75? this number might change)
3. Generate a new RGB histogram of the image
4. Normalize histogram values to get full range of color (I'm not sure if this step is going to make the image look weird, we will have to see with implementation)

## Some Concerns or unorganized thoughts I have
- If there is too much change from frame to frame will the color correction look unnatural or weird
  - How could we do this sequentially? Perhaps tracking the amount of shift in each frame and graphing it, making the shift smoother focusing on peaks and pits and having values in between slowly transition between them?
- I'm going to have to change the values and play around with it, I am wondering if the values need to change for videos taken at different depths


## Thoughts on Language
Python is probably easier to use than C++ with OpenCV, but I do have concerns about speed with long videos. Since all my processing is on a laptop, I don't want to need hours for just a few minutes of high definition (4-5K) video. Still thinking on it, since I don't have a C++ Environment set up right now. I think I will start in python, but honestly it might be better to save myself some time and just start in C++.

Python
+ Easier to develop in
+ Easier environment to set up on a different machine
+ no pesky quirks of C++
- Going to be slower

C++
+ Faster Language (important for end product)
- annoying to work in on this machine
- might not move over to other machines as easily
