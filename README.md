# Virtual-mouse-using-hand-gestures
Instead of a physical mouse, a real-time camera that recognises hand landmarks and analyses gesture patterns was used to create an AI-based method for controlling mouse movement. 
With help of this code, we can use our hands to operate the mouse and do actions such as clicking, double click, drag etc.

# About
This Virtual Mouse Hand Recognition application uses a simple colour cap on the finger without the additional requirement of the hardware for the controlling of the cursor using simple gestures and hand control. This is done using vision based hand gesture recognition with inputs from a webcam. 

In this project, there is use of python libraries such as numpy, autopy ,mediapipe. Numpy is used for handling arrays as well as for the math. MediaPipe is a framework mainly used for building audio, video, or any time series data. With the help of the MediaPipe framework, we can build very impressive pipelines for different media processing functions.

 
![pic 1](https://user-images.githubusercontent.com/53009277/215038426-13a19de5-ceac-4c4c-a4ad-8a7310be0221.png)

Hand landmark model numbering:

As shown in the figure, the MediaPipe uses a single-shot palm detection model and once that is done it performs precise key point localization of 21points 3D palm coordinates in the detected hand region. The MediaPipe pipeline utilizes multiple models like, a palm detection model that returns an oriented hand bounding box from the full image. The cropped image region is fed to a hand landmark model defined by the palm detector and returns high-fidelity 3D hand key points.
In handtracking module there is class called handDetector with 2 functions named findHand ,findPosition, fingerUp and findDistance. The function findHands will accept an RGB image and detects the hand in the frame and locate the key points and draws the landmarks, the function findPosition will give the position of the hand along with the id. The function fingerUp is  used for the number of fingers are up such as index and middle finger for the further work and findDistance is used to find distance between the 2 fingers index and middle one. Then the main function where we initialize our module and also we write a while loop to run the model. Here we can import this setup or the module to the Virtual-mouse project.

In the Virtual-mouse module, there are few steps to complete the task.
1.	Find hand landmarks
2.	Get the tip of the index and middle finger
3.	Check which fingers are up
4.	Only index finger in moving mode
  •	Convert coordinates
  •	Smoothen values
  •	Move mouse
5.	Both index and middle fingers are up then clicking mode
  •	Find distance between fingers
  •	Click mouse if distance is short
  •	Frame rate
  •	Display

# Output
![h1](https://user-images.githubusercontent.com/53009277/215038713-e8400741-b202-4859-969c-70a73c9839cc.png)
![h2](https://user-images.githubusercontent.com/53009277/215038721-944fe248-70de-48f2-adcd-e1c67259fb68.png)

Hand tracking module class output for one hand
 
![h3](https://user-images.githubusercontent.com/53009277/215038792-94d9640d-382d-4b63-86a9-3ed147c9a63b.png)

Hand tracking module class output for both hands

![h4](https://user-images.githubusercontent.com/53009277/215039355-9665430b-9d33-4769-879e-a24a83d07fca.png)
![h5](https://user-images.githubusercontent.com/53009277/215039027-f25a00bf-eef1-458f-9631-0c842bf19e3b.png)

AI Virtualmouse module output



