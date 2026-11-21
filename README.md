# IMPLEMENTATION-OF-EROSION-AND-DILATION-USING-OPENCV

## Aim

To write a Python program using OpenCV to perform morphological operations such as Erosion and Dilation on an image.

The program performs the following operations:

- Image Erosion
- Image Dilation

---

## Software Required

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (`cv2`)
- NumPy
- Matplotlib

---

## Developed By

- **Name:** SHRIVARSHAN P G
- **Register No:** 212225240146

---

## ⚙️ Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Create a blank image using NumPy.

### Step 3:
Insert text onto the image using OpenCV's text drawing function.

### Step 4:
Display the original image.

### Step 5:
Create a structuring element (kernel) of suitable size using `cv2.getStructuringElement()`.

### Step 6: Image Erosion

- Apply the erosion operation using the created kernel with `cv2.erode()`.
- Remove pixels from the boundaries of foreground objects.
- Display the eroded image.

### Step 7: Image Dilation

- Apply the dilation operation using the same kernel with `cv2.dilate()`.
- Add pixels to the boundaries of foreground objects.
- Display the dilated image.

### Step 8:
Compare the original, eroded, and dilated images.

---

## Program

### 1. Original Image

```python
import cv2
import matplotlib.pyplot as plt

# Create a blank image
image = np.zeros((500, 500, 3), dtype=np.uint8)

# Add text on the image using cv2.putText
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(image, 'Shrivarshan', (100, 250), font, 1, (255, 255, 255), 2, cv2.LINE_AA)

# Display the input image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for displaying
plt.title("Input Image with Text")
plt.axis('off')

# Create a simple square kernel (3x3)
kernel = np.ones((3, 3), np.uint8)

# Apply erosion (shrinking effect)
eroded_image = cv2.erode(image, kernel, iterations=1)

# Display the eroded image
plt.imshow(cv2.cvtColor(eroded_image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB
plt.title("Eroded Image")
plt.axis('off')


# Apply dilation (expanding effect)
dilated_image = cv2.dilate(image, kernel, iterations=1)


# Display the dilated image
plt.imshow(cv2.cvtColor(dilated_image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB
plt.title("Dilated Image")
plt.axis('off')

```

## Output

### Original Image with text

<img width="503" height="520" alt="image" src="https://github.com/user-attachments/assets/285b3d38-dc06-46ae-a753-aed34946605e" />


### Erosion

<img width="492" height="502" alt="image" src="https://github.com/user-attachments/assets/243c2be0-2b89-454a-abd7-5e40a85df3cb" />


### Dilation

<img width="495" height="516" alt="image" src="https://github.com/user-attachments/assets/ee3cb5bb-32a6-4042-b145-9a7abb21ee39" />


---

## Result

Thus, the morphological operations Erosion and Dilation were successfully implemented using OpenCV. Erosion reduces the boundaries of foreground objects, whereas Dilation expands their boundaries.
