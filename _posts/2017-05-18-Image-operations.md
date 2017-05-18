---
layout: post
title: Image operationes
tags: 
- Python Study
---
Image operation cases: 1.Add text to image; 2.Resize multiple images.

### Case 1: Add  a number on the picture
Question:
Put a red number on the upper right corner of your profile picture, similar to the effect of numbers of unread messages.

Steps:

* Get the path and name of image.

Here I use sys.argv() to get the path and name of the image.

```python
import sys

if __name__ == '__main__':
    add_number(sys.argv[1]) 
```
Remember that sys.argv[0] is the name of the script. sys.argv[1] is what I needed   

* Get the path of image

I use a regular expression to describe then path, then save it into "path" viable.

```python
pattern = re.compile('(.*\/).*')
    path = re.findall(pattern,path_file)[0]
    
'''The idea is to capture all the content to the last slash by using (.*\/) 
and discard the rest .*. '''

```

* Add a text to image

PIL have a methode as below: 

```python
ImageDraw.Draw.text(xy, text, fill=None, font=None, anchor=None)
```
We need to find a font for our text.
It takes me a while to find a useable font file in my Macbook.
```/System/Library/Fonts/Apple Symbols.ttf
```

#### Here is the complete code:

```python

from PIL import Image
from PIL import ImageFont
from PIL import ImageDraw 
import sys
import re



def add_number(path_file):
    im = Image.open(path_file)
    
    pattern = re.compile('(.*\/).*')
    path = re.findall(pattern,path_file)[0]
    # get a jpeg file
    font = ImageFont.truetype('/System/Library/Fonts/Apple Symbols.ttf', 50) 
    #get a font type file,and size 
    draw = ImageDraw.Draw(im) 
    #get a draw object
    w,h = im.size 
    draw.text((w-50,0), "8", (255,0,0), font=font)
    # locate "8" at right-up corner
    im.save((path+"add number.jpeg"), "jpeg") 

if __name__ == '__main__':
    add_number(sys.argv[1]) 

```
The result looks like this:

![test](https://github.com/JingQin-JQ/learning-python/blob/master/one-code-per-day/add%20number.jpeg)

### Case 2: Resize all pictures in a folder
Question:
There is a folder, have a lot of photos, resize them into no more than the size of iPhone5 resolution.

Steps:
  
  * What does iPhone5 resolution means?
  
 640*1136 pixel (or smaller)
 
  * How to keep the original width/height ratio of pictures when resize them.
  
    * We don't need to resize it if the picture is smaller than 640*1136.   
    * Because we also don't want to change the width/height ratio of pictures. So we need to resize according to the bigger diffrence between height and width.
  
  ```python
  rate = max(img.size[0]/640.0 if img.size[0] > 640 else 0, img.size[1]/1136.0 if img.size[1] > 1136 else 0)
  ```
 
 * Get all image files from a folder
 
 We defined a function called "run" to use os.walk to go through all the path of given folder, and get all image fils for function "process_image" to resize.
 
 ```python
 def run(path_file): #get all pictures from folder
    imgTypes = ['.png','.jpeg','.bmp','.JPG']
    pattern = re.compile('(.*\/).*')
    path = re.findall(pattern,path_file)[0]
    for root, dirs, files in os.walk(path):
        for name in files:
            if os.path.splitext(name)[1] in imgTypes:
                img_file = img.open(path + name)
                process_image(img_file,os.path.splitext(name),path)
 ```
 
 * Resize all pictures and save them
 
 Function "process_image" takes image them selves, their names and their pathes as prameters, resize images by using "thumbnail ", then save them.
 
#### Here is the complete code:
```python
from PIL import Image as img
import os
import os.path
import sys
import re

def run(path_file): #get all pictures from folder
    imgTypes = ['.png','.jpeg','.bmp','.JPG']
    pattern = re.compile('(.*\/).*')
    path = re.findall(pattern,path_file)[0]
    for root, dirs, files in os.walk(path):
        for name in files:
            if os.path.splitext(name)[1] in imgTypes:
                img_file = img.open(path + name)
                process_image(img_file,os.path.splitext(name),path)

def process_image(img,name,path): # resize pics to 640*1136(or smaller)
    rate = max(img.size[0]/640.0 if img.size[0] > 640 else 0, img.size[1]/1136.0 if img.size[1] > 1136 else 0)
    # get a rate for resize
    if rate:
        img.thumbnail((img.size[0]/rate, img.size[1]/rate))
    img.save(path + name[0]+"resize"+".jpeg", "jpeg")            

if __name__ == '__main__':
    run(sys.argv[1])   
```
    