# EXP-1-Image-Handling-and-Pixel-Transformations-Using-OpenCV-Completion-requirements
## Name: BAVYA SRI B 
## Reg. No: 212224230034


## **Aim**
Write a Python program using OpenCV that performs the following tasks:

1.Read and Display an Image.

2.Adjust the brightness of an image.

3.Modify the image contrast.

4.Generate a third image using bitwise operations.

---
## **Software Required:**
1.Anaconda - Python 3.7

2.Jupyter Notebook (for interactive development and execution)

---

## **Algorithm:**
**Step 1:**

Load an image from your local directory and display it.

**Step 2:**

Create a matrix of ones (with data type float64) to adjust brightness.

**Step 3:**

Create brighter and darker images by adding and subtracting the matrix from the original image.
Display the original, brighter, and darker images.

**Step 4:**

Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix).
Display the original, lower contrast, and higher contrast images.

**Step 5:**

Split the image (boy.jpg) into B, G, R components and display the channels

## Program Developed By:
- **Name:** BAVYA SRI B
- **Register Number:** 212224230034


#### Step 1: Read and Display an Image
```python
import cv2
import matplotlib.pyplot as plt
img = cv2.imread(r'D:\Screenshots\Bavya.jpeg', cv2.IMREAD_COLOR)

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()
```
<img width="360" height="510" alt="image" src="https://github.com/user-attachments/assets/9e20014e-f5ff-4e3b-bc58-5d782e449b13" />

#### Step 2: Draw Shapes and Add Text
#####2.1 Draw a Line
```python
image = cv2.imread(r'D:\Screenshots\Bavya.jpeg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape

# Draw a line from top-left to bottom-right
line_img = cv2.line(img_rgb, (0, 0), (1200, 1600), (0, 0, 255), 5) # cv2.line(image, start_point, end_point, color, thickness)

plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()
```
<img width="351" height="502" alt="image" src="https://github.com/user-attachments/assets/101302a5-f02d-4f3f-9b84-6103d1b5ee2c" />


##### 2.2 Draw a Circle

```python
image = cv2.imread(r'D:\Screenshots\Bavya.jpeg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

img_rgb.shape

circle_img = cv2.circle(img_rgb,(640,420),150,(255,0,0),10) # cv2.circle(image, center, radius, color, thickness)

# Display the image
plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()
```
<img width="357" height="505" alt="image" src="https://github.com/user-attachments/assets/3c98d9e5-e692-4347-8a01-8c0991ed33bc" />


##### 2.3 Draw a Rectangle
```python
image = cv2.imread(r'D:\Screenshots\Bavya.jpeg') 

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

img.shape

rectangle_img = cv2.rectangle(img_rgb, (5, 0), (1200, 1590), (0, 0, 255), 20)  

plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()
```
<img width="357" height="510" alt="image" src="https://github.com/user-attachments/assets/cb189a73-8105-4e73-bffd-ad97051d740b" />

#### 2.4 Add Text to the Image
```PYTHON
image = cv2.imread(r'D:\Screenshots\Bavya.jpeg')

# Convert BGR to RGB
img_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

# Add text to the image
text_img = cv2.putText(img_rgb, "OpenCV Drawing", (2, 60),
                       cv2.FONT_HERSHEY_SIMPLEX, 2, (0, 0, 0), 10)

# Display the image
plt.imshow(text_img)
plt.title("Image with Text")
plt.axis('off')
plt.show()
```
<img width="360" height="511" alt="image" src="https://github.com/user-attachments/assets/39273bb5-3170-4521-83c4-c7e2469851bd" />

#### Step 3: Color Space Conversion
```python
img = cv2.imread(r'D:\Screenshots\Bavya.jpeg')

# Check whether the image loaded successfully
if img is None:
    print("Error: Image not found. Check the file path.")

else:
    # Convert BGR to RGB
    image_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

    # Original RGB Image
    plt.figure(figsize=(15, 8))

    plt.subplot(2, 3, 1)
    plt.imshow(image_rgb)
    plt.title("Original RGB Image")
    plt.axis("off")

    # Convert RGB to HSV
    image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)

    plt.subplot(2, 3, 2)
    plt.imshow(image_hsv)
    plt.title("HSV Image")
    plt.axis("off")

    # Convert RGB to Grayscale
    image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)

    plt.subplot(2, 3, 3)
    plt.imshow(image_gray, cmap='gray')
    plt.title("Grayscale Image")
    plt.axis("off")

    # Convert RGB to YCrCb
    image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)

    plt.subplot(2, 3, 4)
    plt.imshow(image_ycrcb)
    plt.title("YCrCb Image")
    plt.axis("off")

    # Convert HSV back to RGB
    image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)

    plt.subplot(2, 3, 5)
    plt.imshow(image_hsv_to_rgb)
    plt.title("HSV to RGB Image")
    plt.axis("off")

    plt.tight_layout()
    plt.show()
```
<img width="1102" height="706" alt="image" src="https://github.com/user-attachments/assets/bf628df0-295a-48e2-a3ab-e484bafbcfe8" />


#### Step 4: Pixel Manipulation
```python
image[200:500, 200:500] = [255, 255, 255]  # Rows: 200-499, Columns: 200-499

image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()
```
<img width="292" height="406" alt="image" src="https://github.com/user-attachments/assets/259be870-b06e-4050-84e3-bb2984dbd1b8" />


#### Step 5: Image Resizing
```python
image = cv2.imread(r'D:\Screenshots\Bavya.jpeg') 
image.shape

# Resize the image to half its size
resized_image = cv2.resize(image, (768 // 2, 600 // 2))  # (new_width, new_height)

# Convert BGR to RGB for displaying with Matplotlib
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)

resized_image_rgb.shape

# Display the resized image
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
```


#### Step 6: Image Cropping
```python
image = cv2.imread(r'D:\Screenshots\Bavya.jpeg')

image.shape

# Crop a 300x300 region starting from (50, 50)
roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349

# Convert BGR to RGB for displaying with Matplotlib
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)

# Display the cropped region (ROI)
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
```
<img width="372" height="407" alt="image" src="https://github.com/user-attachments/assets/6299daa7-2320-4521-8cb1-12ca14d0c666" />

#### Step 7: Image Flipping
```python
image = cv2.imread(r'D:\Screenshots\Bavya.jpeg') 
flipped_horizontally = cv2.flip(image, 1)
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")

flipped_vertically = cv2.flip(image, 0)

flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)

plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
```
<img width="277" height="402" alt="image" src="https://github.com/user-attachments/assets/77ecf17e-0085-44c2-b484-554b7dff0bda" />

<img width="287" height="412" alt="image" src="https://github.com/user-attachments/assets/9b4ac182-9958-4f6d-978b-618bf6dfca6f" />



## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.
