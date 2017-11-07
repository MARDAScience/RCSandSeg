# RCSandSeg

[![DOI](https://zenodo.org/badge/109897334.svg)](https://zenodo.org/badge/latestdoi/109897334)


Program for Interactive Sandbar Segmentation using GrabCut algorithm.

For interactive segmentation of sandbars in imagery from remote cameras in Grand Canyon. Accompanies the following report

```
Grams, Tusso, Buscombe (2017) Automated Remote Cameras for Monitoring Alluvial Sandbars on the Colorado River in Grand Canyon, Arizona. U.S. Geological Survey Open File Report 2017-xxxx
```

This report is hereafter refered to as Grams et al. (2017). This program was written by Daniel Buscombe, USGS and NAU in 2016 and 2017.

## Help
Bugs/comments/questions: daniel dot buscombe at nau dot edu

We assume you have some familiarity with installing and running python programs, and will only answer queries that are specifically related to the program. In other words, do not expect us to teach you how to install or use python or the program's dependencies. For example, we will not help you install git, opencv, or matplotlib. That is up to you. 

## Obtaining the Program
The program can be obtained from https://github.com/dbuscombe-usgs/RCSandSeg

Using git, clone the repository using, from a command window: 

```
git clone git@github.com:dbuscombe-usgs/RCSandSeg.git
```

or, using the 'Clone or Download button', download the zipped archive and unzip to a suitable place on your computer.  


## Before You Start

### Setting up the database
The program is designed to process imagery organized in a specific way. Imagery, obtained from USGS Grand Canyon Monitoring and Research Center data servers, should be organized by site within a root directory. You need to tell the program where the root directory is on your local computer

Open 'RCSandSeg.py' in your favourite text editor (such as Notepad++, Atom, WordPad) and navigate to the line that says

```
rootfolder = '/myfiles/SANDBAR_REMOTECAMERAS/'
```

and replace with the path specific to your local computer, such as 

```
rootfolder = 'E:\DATA\Sandbar_Imagery\'
```

Note on Windows operating systems you may have to use "raw string" notation, such as 

```
rootfolder = r'E:\DATA\Sandbar_Imagery\'
```

### Installing Program Dependencies

The following python libraries are required:

1. opencv
2. matplotlib
3. scipy
4. numpy
5. scikit-image

There are countless thousands of pages on the internet containing guides for how install these programs for your specific operating system, python version, and system architecture. If you are a Windows user and new to python, we suggest using the Anaconda distribution

https://www.anaconda.com/download/

Once installed, open the Anaconda Prompt and type

```
conda install numpy
conda install scikit-image
conda install anaconda-client
conda install --channel https://conda.anaconda.org/menpo opencv3
```

To check opencv is installed correctly, in the Anaconda Prompt type

```
python
```

to get you into a python terminal, then

```
import cv2
cv2.__version__
```

The screen should say '3.X.X' (depending on the latest version of opencv, the Xs could be any number). These instructions were correct at time of writing (November 2017) 


## How to Run
Open a command prompt, navigate to where the program has been downloaded, such as

```
cd C:\Users\user\my_programs\RCSandSeg
```

type:

```
python RCSandSeg.py
``` 

and hit the Enter key.

## How to Use
The program is a single graphical user interface with three tabs. The basic functionality of the program is described in Grams et al. (2017), including the purposes of the three separate tabs.

To test the program, some imagery has been supplied in the 'misc_selection' folder which contains imagery from selected sites. From the gold tab, select these images using the 'Get image files' button, then hit 'Process'

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


## Output Data

The program outputs data to the pickle format with the .p file extension. These files are stored in the folder 'seg_results'. To access this data, use the pickle or cPickle library. The data is a python dictionary (dict) object. From the terminal window, for example:

```
cd seg_results
python
import pickle
with open('RC0089L_20130506_1045.jpg_out.p', 'rb') as f:
   data = pickle.load(f)  
data.keys()
```
will print the variables in the dictionary

```
['contour_x', 'contour_y', 'img', 'bg_x', 'bg_y', 'rect_y', 'rect_x', 'scale', 'fg_x', 'fg_y', 'out_img']
```

The image with sandbar outline can be plotted like so:

```
import matplotlib.pyplot as plt
plt.imshow(data['img'])
plt.plot(data['contour_x'], data['contour_y'], 'r', lw=2)
plt.show()
```



