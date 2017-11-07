# RCSandSeg
Program for Interactive Sandbar Segmentation using GrabCut algorithm.

For interactive segmentation of sandbars in imagery from remote cameras in Grand Canyon

A Program by Daniel Buscombe, USGS and NAU
Bugs/comments/questions: daniel.buscombe@nau.edu
2016 -- 2017

## Before You Start
Open 'RCSandSeg.py' in your favourite text editor (such as Notepad++, Atom, WordPad) and navigate to the line that says

```
rootfolder = '/myfiles/SANDBAR_REMOTECAMERAS/'
```

## How to Run
Open a command prompt and type

```
python RCSandSeg.py
``` 

and hit the Enter key.

## How to Use
Two windows will show up, one for input (your annotations) and one for output (the segmented sandbar).

At first, in input window, draw a rectangle around the object using
mouse right button. Then press 'n' to segment the object (once or a few times)
For any finer touch-ups, you can press any of the keys below and draw lines on
the areas you want. Then again press 'n' for updating the output.

Key '0' - To select areas of sure background
Key '1' - To select areas of sure foreground

Key 'n' - To update the segmentation
Key 'r' - To reset the setup
Key 's' - To save the results