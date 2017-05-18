---
layout: post
title: Transform a picture to character painting
tags: 
- Python Study
---
Study notes about a small program to transform a picture to character painting

### PIL
The Python Imaging Library (PIL) adds image processing capabilities to your Python interpreter. This library supports many file formats, and provides powerful image processing and graphics capabilities.

##### Project description

Picture transfer  to  character painting.
 
* Read the image
* Resize picture
* Use the grayscale value formula to map the RGB values of pixels to the grayscale values,
* Print out character painting

```python
from PIL import Image


ascii_char = list("$@B%8&WM#*oahkbdpqwmZO0QLCJUYXzcvunxrjft/\|()1{}[]?-_+~<>i!lI;:,\"^`'. ")


def getstr(r,g,b,alpha=256):
    ''' 
    make pixel to chars
    '''

    if alpha==0: 
        return ' '
    lens=len(ascii_char)

   
    gray=int(0.2126 * r + 0.7152 * g + 0.0722 * b)

    unit=257.0/lens
    char=ascii_char[int(gray/unit)]

    return char


picture_name=raw_input('please input picture name---->')
size=raw_input('please input size you want like 30x30 or enter to default---->')
a=size.split('x')
width=int(a[0]) if size else 40
height=int(a[1]) if size else 40


im=Image.open(picture_name)

im=im.resize((width,height),Image.NEAREST)


txt=''


for i in range(height):
    for j in range(width):
        txt+=getstr(*im.getpixel((j,i)))
       
    txt+='\n'

print txt
    
with open('output.txt','w') as e:
    e.write(txt)
    e.close()
```
```
input:

Hello-Kitty-Doctor-Who-Weeping-Angel-Die-Cut-Vinyl-Decal-PV1972.png

50x30 
output:

          '$$$'                  .$$$$$.
          $.  .$$$          $$.$$$.   Z$
          $       $$$$$$$$@$  $       ]$
          $.              $    $.$$   $$
          $$@             $    @   B$$$$$
         $$                 $$$$;$$.$   $
        $$                        $$  $$.
        $                          .$$  $
       d$                               $|
       $$                               $$+
     .$$$.      .@o           .$L       $)$w
     $W $$   `$"   @         $$  $$$   B$ $
    @.n ^@$  8     O$        $     W @$$ (a@$.
    $$ J$'$$$@I    $   %  U  $     &$$$$ $.B$.
    $$ $ $ $.$     $         &$     $*$ $$$$ $
     $p.$$$a$     $$$$$$$$$$$$$d     $   $.$$$
     t $$"w.$.  .$$'         .$$$    $ $ $$$>&
      C.$ $ta$$$$  .Q$$$$$$$$'  .$$$$$ u$$$$ @
    $ $h@ $ \ @$                 `$u $      ($
    $  z ;l$   $$$$$$O     :8$$$$$$'  x.$U@
    $  $ $ $  U$                  L$  $ -  $B.
     :$   $$  $.                   $X  $ $  $
     $ '$ 0. n$                    >$ .$ $  J
      o  $   $                      $' $ '.$
      .   +  $                      $@  $  I
          Q  $                      $$  $$!
            .$$$$ '             .?$$B
                  $$$$$$$$$$$$$$
                  
```
  