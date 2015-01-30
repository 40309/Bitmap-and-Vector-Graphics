#Images

Attempt the following programming exercises.

This set of tasks focuses on understanding how images are represented by computers.

##Netpbm Graphics Format

The **Netpbm** graphics format provides a way for you to represent images as a string of text. This makes it very easy to create simple images in just a text editor or from within a program. Normally it is converted to another format before saving as it is very **inefficient** in terms of storage space but for this set of tasks that is an unnecessary additional step.

The format defines **three** ways to store images:

- **PBM** - Portable Bitmap Format
    - Black and white images
    - .pbm file extension
- **PGM** - Portable Graymap Format
    - Greyscale images (upto 256 shades)
    - .pgm file extension
- **PPM** - Portable Pixmap Format
    - Colour images (upto 256 shades for each of Red, Green and Blue)
    - .ppm file extension

###Creating Netpbm Files
To create images you will need to provide:

- image meta data
    - The format used
    - The number of columns in the image
    - The number of rows in the image
- a value for each pixel

####Black and white images
An example of a black and white **pbm** representation of the letter '**A**' might be:

```
P1
9 8
0 0 0 0 1 0 0 0 0
0 0 0 1 0 1 0 0 0
0 0 1 0 0 0 1 0 0
0 0 1 0 0 0 1 0 0
0 0 1 1 1 1 1 0 0
0 0 1 0 0 0 1 0 0
0 0 1 0 0 0 1 0 0
0 0 1 0 0 0 1 0 0
```

The above representation would result in the following image:

![Representation of the Letter A](https://www.dropbox.com/s/sald8dzucd4ovdb/lettera.jpg?dl=1)

Notice that the **meta data** for the image comes first:

- **P1** - this means a **pbm** (black and white) image
- **9 8** - this means that the image has **9 columns** and **8 rows**

The meta data is followed by each row of the image:

- **0** represents **white**
- **1** represents **black**
- there is a **space** between each column value
- there is a **new line** character at the end of each line (this is invisible)
    - in a **text editor** hit the **return** **enter** key for a **new line** character
    - in **Python** add ````\n```` to a string to represent a **new line** character

####Greyscale images
An example of a greyscale **pgm** representation of the letter '**M**' might be:

```
P2
10 10
255
0 10 20 50 80  0   0 0 0 0
0 10  0  0  0 80   0 0 0 0
0 10  0  0  0  0 120 0 0 0
0 10  0  0  0  0 120 0 0 0
0 10  0  0  0 80   0 0 0 0
0 10 20 50 80  0   0 0 0 0
0 10  0  0  0 80   0 0 0 0
0 10  0  0  0  0 120 0 0 0
0 10  0  0  0 80   0 0 0 0
0 10 20 50 80  0   0 0 0 0
```
The above representation would result in the following image:

![Representation of the Letter B](https://www.dropbox.com/s/v077hd70464itzz/letterb.jpg?dl=1)

Notice that there is an **additional row** of **meta data**. This represents the **maximum grey value** allowed. It can be anything from **0 to 255**.

Rather than representing each pixel with a 0 or 1, in a greyscale image a number between 0 (white) and the maximum grey value (black) is provided instead.

####Colour images
An example of a colour **ppm** representation of a smiley face might be:

```
P3
10 10
255
255 255 255 255 255 255 255 255 255 247 237 0 247 237 0 247 237 0 247 237 0 255 255 255 255 255 255 255 255 255
255 255 255 255 255 255 247 237   0 247 237 0 247 237 0 247 237 0 247 237 0 247 237   0 255 255 255 255 255 255
255 255 255 247 237   0 247 237   0 247 237 0 247 237 0 247 237 0 247 237 0 247 237   0 247 237   0 255 255 255
247 237   0 247 237   0 247 237   0   0   0 0 247 237 0 247 237 0   0   0 0 247 237   0 247 237   0 247 237   0
247 237   0 247 237   0 247 237   0 247 237 0 247 237 0 247 237 0 247 237 0 247 237   0 247 237   0 247 237   0
247 237   0 247 237   0 247 237   0 247 237 0 247 237 0 247 237 0 247 237 0 247 237   0 247 237   0 247 237   0
247 237   0 247 237   0   0   0   0 247 237 0 247 237 0 247 237 0 247 237 0   0   0   0 247 237   0 247 237   0
255 255 255 247 237   0 247 237   0   0   0 0 247 237 0 247 237 0   0   0 0 247 237   0 247 237   0 255 255 255
255 255 255 255 255 255 247 237   0 247 237 0   0   0 0   0   0 0 247 237 0 247 237   0 255 255 255 255 255 255
255 255 255 255 255 255 255 255 255 247 237 0 247 237 0 247 237 0 247 237 0 255 255 255 255 255 255 255 255 255
```

The above representation would result in the following image:

![Smiley Face](https://www.dropbox.com/s/cfk0l06rrixjagg/smiley.jpg?dl=1)

Notice that in a colour image **three values** are provided for each pixel:

- Red (0-255)
- Green (0-255)
- Blue (0-255)

Here white is (255, 255, 255) and black is (0, 0, 0).

##Tasks

You will need the following Python files in the **same directory** as the programs you will create for these tasks:

- netpbmfile.py
- image_tools.py

At the top of your programs you will need the following line:

```python
from image_tools import *
```

You will need to make use of the available functions:

```python
#displays the image with the given file name
show_image('image_name.ppm')

#creates a new file with the given file name containing the contents of the provided string
save_image('image_name.ppm', image_string)
```

##Task 1
In a text editor create a **black and white** representation of your first name (or shortened version if your name is long). Once you have saved the representation with the **appropriate** file extension, write a program that will display the image representation of your name.

##Task 2
Write a program that will allow a user to enter a **single** word. The program will then convert this word **upper-case** and then into a **black and white** image. This image will then be displayed to the user.

###Helpful hints

- It may be useful to work as a group for part of this assignment as you will need representations for every letter in the alphabet (upper-case only).
- Use a grid system for the letters - say 10x10 pixels. This will make the task easier.
- Think about the **string splitting** operations you are aware of. You will need these.
- Remember that a new line character is needed at the end of each line of the image. In Python the new line character is `\n`.

##Task 3
Improve your program from Task 2 so that the user can request that each letter is drawn in a different shade of grey.

##Task 4
Improve your program from Task 3 so that the user can provide the precise colours for each letter of the entered word.
