# Intelligent Placer Python Project
---

## Abstract
The name of the project is «Intelligent Placer». Formulation of the problem is given below.  

__Input:__ pictures showing object A – 10 liter plastic lilac pelvis, and object B – a table with table top in dark brown and beige shades, having a set of straight parallel lines on the table top, and 4 glossy metal legs.  
We aim of the project is to understand wether object A can be placed under table B. “Place” means movement of object A in one plane to the area under the table top of object B without deforming object A.  

__Output:__ the answer „yes“ if the object A can be placed under object B, and “no” otherwise.  

__Important note:__ an object A can be placed under the table B if its dimentions are smaller than the distance from the floor to the tabletop. The pelvis satisfies this condition in advance. It is forbidden for pelvis to hang above the table: it can only lie on the floor, in contact or not with the legs, or on the tabletop itself. Thus, the answer "no" is obtained when the pelvis is above the table or at the level of the tabletop. The answer "yes" is obtained when the pelvis is under the table (under the tabletop).  
In this way the aim of the project is to understand, where is the pelvis: under the table or on the table.  

## Design and Technology
This is computer vision project, so the most of important used libraries are about CV and image processing. These are:  
-	`matplotlib >= v.3.4.1` – helps to show the images in jupyter notebook
-	`numpy >= 1.20.2` – used to represent the image as pixels array
-	`opencv-python >= 4.5.1.48` – used to read an image, understand the colours, find bounding box of the object etc.
-	`scikit-image >= 0.18.1` – has important image filters: gaussian, canny. Also is used for Hough transform
-	`scipy >= 1.6.2` – helps to work with masks: binary closing/opening
-	`Shapely >= 1.7.1` – is used to work with lines (because they are representing the table)

## Interfaces and input data
Basically, there won’t be any interfaces provided – this is the computational and algorithm-creating task for the most part. So the solution will be given step-by-step in the jupyter notebook with showing results of each part of the algorithm.   

__Input data requirements:__  
-	Image format should be Joint Photographic Experts Group (.jpeg, .jpg), aspect ratio 9:16 (landscape). The minimum image size is 360 x 640.
-	Objects on the photo are clearly distinguishable: sharp, not blurred, in focus, not noisy, there is no retouching; no overexposed or black areas, colors are natural.
-	The background behind the studied objects is light, contrasting with both objects and their parts.
-	The proportions of objects relative to each other are preserved. The objects are in the photo as a whole, i.e. are not clipped at the edges of the image. Collages of two or more images are not allowed. Both objects (table B and pelvis A) are necessarily present in the image. The table should be close to the wall (background), most of the tabletop should be parallel (or almost parallel) to the wall.
-	Mid-angle optics is required (fish-eye images are not allowed). Images have little or no perspective distortion.

The input labeled data can be founded by following link:  
https://drive.google.com/drive/folders/1avndVCk5B11ziDMgiSLS7m3qxczAxOmm?usp=sharing

## Made works

Made works step by step you can find in source files. How to run the algorithm?

### Jupyter Notebook
Open `Jupyter Notebook` file **project.ipynb**, run step by step.
### Python file
```{python}
$ git clone https://github.com/adtsvetkov/signals
$ cd signals
$ git checkout develop
$ pip install -r requirements.txt
$ python biglab.py
```
**Note:** in `Jupyter Notebook` is recommended to use `Python v.3.8.4+`.   
`.py`-file was correctly working on `Python v.3.9.4`.  
Test data are also placed in `data`-folder.

## References

For the presented work following sources should be used:
-	https://scikit-image.org/docs/dev/api/skimage.feature.html#skimage.feature.canny – canny filter documentation & usage
-	https://opencv24-python-tutorials.readthedocs.io/en/latest/py_tutorials/py_imgproc/py_houghlines/py_houghlines.html - hough transform tutorials
-	https://docs.opencv.org/3.4/da/d97/tutorial_threshold_inRange.html - usage of `cv.inRange()` function
-	https://docs.opencv.org/4.x/dd/d49/tutorial_py_contour_features.html - openCV contour features tutorial
