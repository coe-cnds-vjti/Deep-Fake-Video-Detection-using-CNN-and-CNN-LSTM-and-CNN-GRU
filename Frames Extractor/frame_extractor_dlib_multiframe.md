This code extracts 30 frames from each of the video.

It uses "mmod_human_face_detector" face detector model.


This detector returns a mmod_rectangles object. This object contains a list of mmod_rectangle objects.
    These objects can be accessed by simply iterating over the mmod_rectangles object
    The mmod_rectangle object has two member variables, a dlib.rectangle object, and a confidence score.
    
Input: Video Dataset

Output: Face dataset

For each video in the dataset, it performs following steps on it:

1. Create directory to store the faces (in the form of images) detected in the frames.
2. Store the count of frames with no faces, more than one faces and faces out of frame and toral processed frames. 
