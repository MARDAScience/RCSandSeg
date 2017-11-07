# RCSandSeg
Program for Interactive Sandbar Segmentation using GrabCut algorithm.

For interactive segmentation of sandbars in imagery from remote cameras in Grand Canyon. Accompanies the following report

```
Grams, Tusso, Buscombe (2017) Automated Remote Cameras for Monitoring Alluvial Sandbars on the Colorado River in Grand Canyon, Arizona. U.S. Geological Survey Open File Report 2017-xxxx
```

A Program by Daniel Buscombe, USGS and NAU. Written in 2016 and 2017

##Help
Bugs/comments/questions: daniel dot buscombe at nau dot edu

We assume you have some familiarity with installing and running python programs, and will only answer queries that are specifically related to the program. In other words, do not expect us to teach you how to install or use python or the program's dependencies. For example, we will not help you install git, opencv, or matplotlib. That is up to you. 

##Obtaining the Program
The program can be obtained from https://github.com/dbuscombe-usgs/RCSandSeg

Using git, clone the repository using, from a command window: 

```
git clone git@github.com:dbuscombe-usgs/RCSandSeg.git
```

or, using the 'Clone or Download button', download the zipped archive and unzip to a suitable place on your computer.  


## Before You Start
The program is designed to process imagery organized in a specific way.

Open 'RCSandSeg.py' in your favourite text editor (such as Notepad++, Atom, WordPad) and navigate to the line that says

```
rootfolder = '/myfiles/SANDBAR_REMOTECAMERAS/'
```

## Install Program Dependencies

## How to Run
Open a command prompt and type

```
python RCSandSeg.py
``` 

and hit the Enter key.

## How to Use
Two windows will show up, one for input (your annotations) and one for output (the segmented sandbar).

At first, in input window, draw a rectangle around the object using
mouse right button. 

Then press 'n' to segment the object (once or a few times)

For any finer touch-ups, you can press any of the keys below and draw lines on
the areas you want. Then again press 'n' for updating the output.

Key '0' - To select areas of sure background

Key '1' - To select areas of sure foreground

Key 'n' - To update the segmentation

Key 'r' - To reset the setup (such as if you make a mistake)

Key 's' - To save the results

