# PAN card tempering detection

[to see the app in live press here](https://pan-card-tampering-detection-107600ec5681.herokuapp.com/)
## Overview

PAN (Permanent Account Number) card detection is a process that involves identifying and verifying PAN cards, which are issued by the Income Tax Department of India. PAN cards are used as a universal identification key for all financial transactions and have significant importance in tax-related processes.

In this project, we will detect tempering of pan card using computer vision. this project will help the different organization in detecting whether the id (the pan card) provided to them by their employees or customers or anyone is original or not.

![](.readmeimages/1.png)
![](.readmeimages/2.png)
## Steps for PAN Card Tempering Detection

### 1. **Get the Images from the User**

Prompt the user to upload the suspected tampered image along with the original pan card image. This is the starting point, where the user provides the necessary input for the detection process.

### 2. **Read and Validate the Image**

Load the uploaded images and validate their formats and sizes (e.g., JPEG, PNG) to ensure they are compatible for processing. This ensures the images are in a usable format and have appropriate dimensions for comparison.

### 3. **Resize the Image to Match the Template**

Adjust the size of the user-provided image to match the dimensions of the original image. Standardizing the image size ensures a fair comparison between the original and the suspect images.

### 4. **Convert the Image to Grayscale**

Convert both images to grayscale to reduce complexity and focus on structural differences. This simplifies the comparison process by removing color information, which is less relevant for tampering detection.

### 5. **Compute the Similarity Index**

Calculate a similarity index (e.g., Structural Similarity Index Measure, SSIM) between the grayscale images. This quantifies the visual similarity between the original and suspect images, with lower scores indicating potential tampering.

### 6. **Detect and Extract Contours**

Identify and extract contours from the difference image using edge detection techniques and tools like `imutils`. Contours highlight the boundaries of regions where significant differences exist, possibly indicating tampering.

### 7. **Draw Bounding Boxes Around Contours**

Draw rectangles around the detected contours to visually mark areas of potential tampering. This clearly indicates the regions in the image where differences were found, making it easier to analyze the tampered areas.

### 8. **Plot the Differences and Thresholded Image**

Display the difference image, a thresholded version of the difference, and the final image with contours highlighted. This provides a visual representation of the tampering, showing the user exactly where the differences are located.

### 9. **Compare All Images and Generate a Similarity Report**

Compare the similarity scores of all images and generate a report indicating whether tampering is detected based on predefined thresholds. This summarizes the findings and provides a clear, actionable result indicating the likelihood of tampering.

### 10. **Output the Final Tampering Detection Result**

Present the final result to the user, including the similarity score and annotated images. This delivers a user-friendly output that highlights potential tampering areas and provides a definitive conclusion.


## Deployment on heroku 

here is the link of the application: 

[heroku-deployment](https://pan-card-tampering-detection-e0dbf45b835c.herokuapp.com)


### note: if you want to deploy on heroku you need to add the heroku-buildpakc-apt and ann libgl1 to the Aptfile

```bash
heroku buildpacks:add --index 1 heroku-community/apt --app appname

libgl1

```