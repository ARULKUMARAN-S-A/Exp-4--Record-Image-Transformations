# Exp-4--Record-Image-Transformations
## Regno: 212224040030
## Name: ARUL KUMARAN S A

## Aim
To capture an image using a webcam and perform various image transformations such as resizing, rotation, flipping, and grayscale conversion using OpenCV.

## Algorithm

### Step 1:
Import the required libraries: OpenCV and Matplotlib.

### Step 2:
Initialize the webcam using `cv2.VideoCapture(0)`.

### Step 3: Image Capturing
- Capture an image using the webcam.
- Read the captured frame.
- Release the webcam.
- Save the original image as `original.jpg`.

### Step 4: Image Resizing
- Resize the captured image to 400 × 300 pixels using `cv2.resize()`.
- Save the resized image as `resized.jpg`.

### Step 5: Image Rotation
- Rotate the original image 90° clockwise using `cv2.rotate()`.
- Save the rotated image as `rotated.jpg`.

### Step 6: Image Flipping
- Perform horizontal flipping using `cv2.flip()`.
- Save the flipped image as `flipped.jpg`.

### Step 7: Grayscale Conversion
- Convert the original color image into grayscale using `cv2.cvtColor()`.
- Save the grayscale image as `grayscale.jpg`.

### Step 8: Display Output
- Display all transformed images using Matplotlib.
- Add suitable titles to each output image.
- Display the images in a single figure.

## Program

```python
import cv2
import matplotlib.pyplot as plt

# Step 1: Capture image using webcam
cap = cv2.VideoCapture(0)

ret, frame = cap.read()
cap.release()

if ret:
    cv2.imwrite("original.jpg", frame)

    # Step 2: Resize image
    resized = cv2.resize(frame, (400, 300))
    cv2.imwrite("resized.jpg", resized)

    # Step 3: Rotate image
    rotated = cv2.rotate(
        frame, cv2.ROTATE_90_CLOCKWISE
    )
    cv2.imwrite("rotated.jpg", rotated)

    # Step 4: Flip image
    flipped = cv2.flip(frame, 1)
    cv2.imwrite("flipped.jpg", flipped)

    # Step 5: Convert to grayscale
    gray = cv2.cvtColor(
        frame, cv2.COLOR_BGR2GRAY
    )
    cv2.imwrite("grayscale.jpg", gray)

    # Step 6: Display all images
    plt.figure(figsize=(12, 8))

    plt.subplot(2, 3, 1)
    plt.imshow(cv2.cvtColor(frame, cv2.COLOR_BGR2RGB))
    plt.title("Original Image")
    plt.axis("off")

    plt.subplot(2, 3, 2)
    plt.imshow(cv2.cvtColor(resized, cv2.COLOR_BGR2RGB))
    plt.title("Resized Image")
    plt.axis("off")

    plt.subplot(2, 3, 3)
    plt.imshow(cv2.cvtColor(rotated, cv2.COLOR_BGR2RGB))
    plt.title("Rotated Image")
    plt.axis("off")

    plt.subplot(2, 3, 4)
    plt.imshow(cv2.cvtColor(flipped, cv2.COLOR_BGR2RGB))
    plt.title("Flipped Image")
    plt.axis("off")

    plt.subplot(2, 3, 5)
    plt.imshow(gray, cmap="gray")
    plt.title("Grayscale Image")
    plt.axis("off")

    plt.tight_layout()
    plt.show()

    print("All images saved successfully!")

else:
    print("Camera not detected!")
```


## Output 

### Original Image
<img width="366" height="295" alt="image" src="https://github.com/user-attachments/assets/106949bd-5f42-40aa-b7ba-3b72b7645fb0" />


### Resized Image
<img width="350" height="296" alt="image" src="https://github.com/user-attachments/assets/3a51077b-7659-422e-92ff-23f617f68e04" />


### Rotated Image
<img width="273" height="362" alt="image" src="https://github.com/user-attachments/assets/0aa302dc-e082-41d1-be10-f90f27051a97" />


### Flipped Image
<img width="361" height="298" alt="image" src="https://github.com/user-attachments/assets/6adc9c50-0842-40bc-b56c-1f1e33eaf55a" />


### Grayscale Image
<img width="360" height="288" alt="image" src="https://github.com/user-attachments/assets/4ff24312-b2ee-4aef-af97-6491629a8741" />



## Result

Thus, an image is successfully captured using a webcam, and various image transformations such as resizing, rotation, flipping, and grayscale conversion are performed using OpenCV. These transformations demonstrate how images can be modified and processed for different computer vision applications.
