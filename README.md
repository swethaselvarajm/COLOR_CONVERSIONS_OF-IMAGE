# COLOR_CONVERSIONS_OF-IMAGE
## AIM
To write a python program using OpenCV to do the following image manipulations.

i) Read, display, and write an image.

ii) Access the rows and columns in an image.

iii) Cut and paste a small portion of the image.

iv)To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Choose an image and save it as a filename.jpg ,
### Step2:
Use imread(filename, flags) to read the file.
### Step3:
Use imshow(window_name, image) to display the image.
### Step4:
Use imwrite(filename, image) to write the image.
### Step5:
End the program and close the output image windows.
### Step6:
Convert BGR and RGB to HSV and GRAY
### Step7:
Convert HSV to RGB and BGR
### Step8:
Convert RGB and BGR to YCrCb
### Step9:
Split and Merge RGB Image
### Step10:
Split and merge HSV Image

##### Program:
### Developed By: SWETHA.S
### Register Number: 212222230155


## Output:

### i) Read and display the image

```
   import cv2
    image=cv2.imread('SWETHA.jpg',1)
    image=cv2.resize(image,(400,300))
    cv2.imshow('SWETHA',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
![SWETHA](https://github.com/swethaselvarajm/COLOR_CONVERSIONS_OF-IMAGE/assets/119525603/e5228c1c-347a-420f-994d-37965a982283)


### ii)Write the image

```
    import cv2
    image=cv2.imread('SWETHA.jpg',0)
    cv2.imwrite('de.jpg',image)
```
![Screenshot 2024-02-17 082503](https://github.com/swethaselvarajm/COLOR_CONVERSIONS_OF-IMAGE/assets/119525603/0629581d-2957-4a67-9c15-d5b2555ba9f4)

### iii)Shape of the Image

```
    import cv2
    image=cv2.imread('SWETHA.jpg',1)
    print(image.shape)
```
![Screenshot 2024-02-17 082545](https://github.com/swethaselvarajm/COLOR_CONVERSIONS_OF-IMAGE/assets/119525603/17c42df2-4b59-4d96-9d2e-0b26f1385080)

### iv)Access rows and columns

```
    import random
    import cv2
    image=cv2.imread('SWETHA.jpg',1)
    image=cv2.resize(image,(400,400))
    for i in range (150,200):
      for j in range(image.shape[1]):
          image[i][j]=[random.randint(0,255),
                       random.randint(0,255),
                       random.randint(0,255)] 
    cv2.imshow('part image',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
![Screenshot (104)](https://github.com/swethaselvarajm/COLOR_CONVERSIONS_OF-IMAGE/assets/119525603/5226d7d3-2e87-4aec-bac2-dd503526263c)


### v)Cut and paste portion of image
```
   import cv2
   image=cv2.imread('SWETHA.jpg',1)
   image=cv2.resize(image,(400,400))
   tag =image[150:200,110:160]
   image[110:160,150:200] = tag
   cv2.imshow('partimage1',image)
   cv2.waitKey(0)
   cv2.destroyAllWindows()
```
![Screenshot (105)](https://github.com/swethaselvarajm/COLOR_CONVERSIONS_OF-IMAGE/assets/119525603/d0bbcbe9-d305-47ec-9151-3b11c0d19c31)


### vi) BGR and RGB to HSV and GRAY
```
import cv2
img = cv2.imread('SWETHA.jpg',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)

hsv1 = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('BGR2HSV',hsv1)

hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',hsv2)

gray1 = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2.imshow('BGR2GRAY',gray1)

gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',gray2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![Screenshot (108)](https://github.com/swethaselvarajm/COLOR_CONVERSIONS_OF-IMAGE/assets/119525603/9d9ec54e-eb53-46b5-8923-590b619bb8fc)


### vii) HSV to RGB and BGR
```
import cv2
img = cv2.imread('SWETHA.jpg')
img = cv2.resize(img,(300,200))

img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)

RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)

BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![Screenshot (109)](https://github.com/swethaselvarajm/COLOR_CONVERSIONS_OF-IMAGE/assets/119525603/57f49b9e-2552-453b-b15c-9c0f4435ce83)


### viii) RGB and BGR to YCrCb
```
import cv2
img = cv2.imread('SWETHA.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![Screenshot (110)](https://github.com/swethaselvarajm/COLOR_CONVERSIONS_OF-IMAGE/assets/119525603/dd0b9186-8487-40c8-8ab7-774a7ffa61d4)


### ix) Split and merge RGB Image
```
import cv2
img = cv2.imread('SWETHA.jpg',1)
img = cv2.resize(img,(300,200))

R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]

cv2.imshow('R-Channel',R)
cv2.imshow('G-Channel',G)
cv2.imshow('B-Channel',B)

merged = cv2.merge((B,G,R))
cv2.imshow('Merged RGB image',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![Screenshot (111)](https://github.com/swethaselvarajm/COLOR_CONVERSIONS_OF-IMAGE/assets/119525603/dff59494-bc46-4ff2-a336-7a79a4a26f0c)

### x) Split and merge HSV Image
```
import cv2
img = cv2.imread("SWETHA.jpg",1)
img = cv2.resize(img,(300,200))
img=cv2.cvtColor(img,cv2.COLOR_RGB2HSV)

H,S,V=cv2.split(img)

cv2.imshow('Hue',H)
cv2.imshow('Saturation',S)
cv2.imshow('Value',V)

merged = cv2.merge((H,S,V))
cv2.imshow('Merged',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![Screenshot (112)](https://github.com/swethaselvarajm/COLOR_CONVERSIONS_OF-IMAGE/assets/119525603/5f0ec5f2-864a-4267-8e64-acea267245af)


## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.
