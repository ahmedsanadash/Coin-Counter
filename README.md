# Coin-Counter
Money Detection and Counting with OpenCV and CVZone

This project uses OpenCV and CVZone to detect coins or objects of a certain color and approximate their value based on size. The system uses a webcam to capture real-time video, processes the frames, detects contours, and calculates the total money.

Features

Real-time detection of objects using a webcam.

Color-based object filtering using HSV values.

Contour detection to estimate object area.

Money estimation based on object size.

Adjustable Canny edge thresholds through trackbars.

Real-time display with stacked images showing the original image, pre-processed edges, detected contours, and the total money counted.

Requirements

Make sure you have Python installed along with the following packages:

pip install opencv-python
pip install cvzone
pip install numpy

Usage

Connect a webcam (your code uses device 1, adjust if needed).

Run the Python script:

python money_counter.py


Adjust thresholds:
Use the "Settings" window trackbars to adjust Threshold1 and Threshold2 for Canny edge detection.

View the output:
The main window will display four stacked images:

Original frame

Pre-processed frame (Canny edges)

Contours detected

Total money counted

Money calculation:

Objects with area < 2050 → Rs. 5

Objects with area between 2050 and 2500 → Rs. 1

Objects with area > 2500 → Rs. 2

How It Works

Video Capture: Captures frames from the webcam using OpenCV.

Preprocessing: Applies Gaussian blur, Canny edge detection, dilation, and morphological closing to highlight object edges.

Contour Detection: Uses CVZone's findContours to detect objects.

Color Detection: Uses HSV filtering to identify objects with a specific color.

Money Estimation: Calculates the total based on detected object areas.

Visualization: Displays processed frames and total money in real-time.

Customization

HSV Color Values:
Modify the hsvVals dictionary to detect a different color.

hsvVals = {'hmin': 0, 'smin': 0, 'vmin': 145, 'hmax': 63, 'smax': 91, 'vmax': 255}


Area thresholds:
Change the area conditions to match the size of your objects.

Trackbars:
Adjust Threshold1 and Threshold2 for better edge detection depending on lighting and object contrast.

Screenshots


Example of the stacked output showing the original, pre-processed, contours, and total money.

Notes

Ensure proper lighting for accurate color detection.

This project works best with a plain background to avoid false positives.

You can add more rules for different coins or objects by changing area ranges and assigned values.

Author

Ahmed Mohamed Abdel Menem
Mechatronics Engineering Student
Email: ahmedsanadash@gmail.com
