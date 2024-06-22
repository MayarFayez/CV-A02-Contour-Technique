# CV-A02 : Contour Technique

## Description:
A small web application based app developed with python and streamlit, to apply different image processing techniques.

## Requirements:
•	Python 3.  
•	Streamlit 1.13.0  
•	Numpy 1.23.4  
•	Matplotlib 3.6.2  

## Running command:
Streamlit run server.py   

-The UI contains two main tabs Hough Transformations, Active Contour  

# Tab1:
•	Line Detection  
•	Circle Detection     
•	Ellipse Detection   

### Line Detection:
#### Algorithm
First: We read image using cv2 library then, apply canny edge detection also using cv2 library.   
Second: Call line detection function with parameters uploaded image, edged image and threshold from user, we want to determine the height & width of edged image to determine the diagonal then, determine “theta” resolution and “r” resolution.  
Then, find all non-zeros edges pixels and cycle through them and cycle through theta to calculate “r” resolution to determine hough accumulator.  
Last step:  Cycle through accumulator to determine line points then, using cv2.line library to superimpose the detected line on the input image.  
#### Parameters that user can enter them:
•	Line Detection Threshold   
•	Canny Edge Lower Threshold  
•	Canny Edge Higher Threshold    
![Screenshot (1470)](https://github.com/MayarFayez/CV_-Contour-Technique-/assets/93496610/08d6b736-23a5-434f-a02b-dc641b8c9b50)  
Result  
![Screenshot (1471)](https://github.com/MayarFayez/CV_-Contour-Technique-/assets/93496610/4f97d563-f364-4155-80d1-a08732afba0a)  

### Circle Detection:
#### Algorithm
First: We read image using cv2 library then, apply canny edge detection also using cv2 library.   
Second: Call circle detection function with parameters uploaded image, edged image, min radius and max radius of detected circle and delta r change from min radius and max radius. Based on defined number of angles we calculate angles from 0 to 360 to build parametric equation of circle (x = x_center + r * cos(t) and y = y_center + r * sin(t)), then append it in array of candidate circles. loop on image height and width of an image to find an edge pixel which pass through any of candidate circle array then build accumulator from defined current circles in image.  
Last step:  Sort accumulator in addition to some post process to exclude too close circles and duplicated ones. Finally using cv2.cirlce library to superimpose the detected circles on the input image.
#### Parameters that user can choose them:
•	Canny Edge Lower Threshold  
•	Canny Edge Higher Threshold  
•	Minimum Circle Radius   
•	Maximum Circle Radius   
•	Change between min radius and max radius.  
![Screenshot (1472)](https://github.com/MayarFayez/CV_-Contour-Technique-/assets/93496610/cea9d7c2-cda1-454e-a2f0-c8492d54a25c)  
Result  
![Screenshot (1473)](https://github.com/MayarFayez/CV_-Contour-Technique-/assets/93496610/9e8385f0-13b2-4a4d-b9ba-c4e3640dc7d7)  
# Tab2:






