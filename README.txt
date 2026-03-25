Hey! Thanks for being interested in my engine!
Here is the format for a .vc file:
-------------------customfile.vc-----------------------
VC PROGRAM FILE 753753753
// the line above must always be at the beginning of any .vc file for it to verify.
// this is a comment

setup:
v==1
res==3
movement==6
fps==20

loop:
erase
// comment
x:v:90:20:#00ff00
v=+1
break
gt loop
------------------end of file--------------------------

Here are the base functions:

// This is a comment

VARIABLES:
v==2 : sets a variable
v=+2 : changes a variable by 2
v=-2 : removes 2 from a variable
v=*2 : multiplies a variable by 2
v=/2 : divides a variable by 2
v==g : sets a variable to another variable

PRESET VARIABLES:
res : necessary for setting the resolution of the screen
movement : will be removed soon
fps : frames per second for speed of updates
mx : the mouse X
my the mouse Y

POINT FUNCTION:
origin X : origin Y : direction : magnitude : color

mx:my:0:0:#00ff00
That would make a green dot wherever the mouse is.

LABELS:
"start:" would create a label named start,
You can move to that line using "gt start",
Alternatively you can go to a specific line using "gt 5"

EXTRA:
break is a function which is necessary for screen updates, I suggest putting it in a loop at the end when you're ready to update the screen.
erase is a function that clears the screen when needed.
