My server: https://discord.gg/u8f8QC7V7k

Hey! Thanks for being interested in my engine!
Here is the format for a .vc file:
-------------------customfile.vc-----------------------
VC PROGRAM FILE 753753753
// the line above must always be at the beginning of any .vc file for it to verify.
// this is a comment

block setup [
v==1
res==3
movement==6
fps==20
]

block loop [
erase
// comment
x:v:90:20:#00ff00
v=+1
break
do loop
]

do setup
do loop
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

MATH OPERATORS:
Along with =, +, -, /, *, 
I added a function for <, >, <=, and >=
"oper v,n>2" would check if "n" is larger than 2, and set "v" to 1 or 0, depending on if it's true or not.

POINT FUNCTION:
origin X : origin Y : direction : magnitude : color
Syntax: x:y:dir:mag:col

mx:my:0:0:#00ff00
That would make a green dot wherever the mouse is.

KEY PRESS:
"kp k,f" sets the variable "k" to 1 or 0 depending on if the F key is pressed.
Syntax: kp var,keyToPress

IF STATEMENT:
"if" chooses whether or not to skip the next line.
"if 1" would run the next line.
"if 0" would skip the next line.
"if v
g==1"
If v equals 1, g will be set to 1, if v equals 0 or anything else, the line will be skipped.

FUNCTION THINGS:
"block setA [
a==5
]"
This will make a function named "setA", but will not run it until
"do setA" is called.
This will be useful, for example, making sprites that would be hard to recreate a hundred times.
Always be sure to put "return" at the end of every function to return to the "do" command.
Syntax: block setA [
        a==5
        return
        ]
        do setA


SIMPLE MOVEMENT BASICS:
One way to do movement is:
"kp key,w
if key
// which means this will run if W is pressed
y=+1
// change the Y var by 1

kp key,s
if key
y=-1
// change the Y var by -1"

Simple Up/Down movement.

EXTRA:
break is a function which is necessary for screen updates, I suggest putting it in a loop at the end when you're ready to update the screen.
erase is a function that clears the screen when needed.
reset is a function that resets the program so you may upload a new file and such,
it is recommended to add these lines to any loop function:
"kp key,r
 if key
 reset"
