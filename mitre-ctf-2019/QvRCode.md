The problem gave you an image which looked like a QR code, but the data section
has colors, whereas a normal QR code does not have any colors.

My initial thouhts were to separate the different color values into different
images, so one image had the red color stream as data, one image had the green
color stream as data, and one image had the blue color stream as data. Then, I
tried scanning the resulting images as QR codes. However, on doing this, only the
red color stream was able to be read as a flag, while the other two streams
weren't able to be read. But the red color stream did have a part of the flag in
it, so I knew I was on the right track.

The next thing I did, was extract the raw pixel values into code and count the
number of differently-colored pixels. I found that there were only 8 different
colors among all of the pixels in the image. So my next thoughts were to just try
all the possible combinations of colors. I wrote a quick python script, using
[PIL](https://pillow.readthedocs.io/en/stable/) and
[pyzbar](https://pypi.org/project/pyzbar/) libraries, which took every possible
mapping of the existing 8 colors into black or white and tried to read it as a QR
code. In the end, there were 3 different combinations that were able to be read
as QR codes, and pieces of the flag were spread up among the three of them.

I won't put the flag here, though, so you can have the fun of finding it
yourself.

