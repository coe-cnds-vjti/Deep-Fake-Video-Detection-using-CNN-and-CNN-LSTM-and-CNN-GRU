# Framing and Face Generation for Datasets 
This code extracts faces from the frames of the videos and stores it in different folders for further training, testing and validation purpose.

It uses the pretrained face detection model: **"mmod_human_face_detector.dat"**

This detector returns rectangles which surround the faces in the video frames.

**Input:** Video dataset

**Output:** Face dataset stored in 3 different folders:

        1. Training (containing extracted face images from first 1800 videos)
        
        2. Validation (containing extracted face images from next 750 videos)
        
        3. Testing (containing extracted face images from remaining videos)

## Algorithm:
1. For each video in the video dataset it follows following steps:
  
    i. Determine in which folder its faces need to be stored depending on its serial number.
     
        If it is less than or equal to 1800 then we have to store its extracted faces in training folder.
        If it is between 1800 and 2500 then we have to store its extracted faces in validation folder.
        and if it is greater than or equal to 2550 then we have to store its extracted faces in testing folder.
        
    ii. Read the video.
    
    iii. Using detector model extract faces from the frames.
    
    iv. Using the co-ordinates of rectangles returned by detector model crop the faces from frames and store those face images in the appropriate folder.
  
