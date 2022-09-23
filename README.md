# napari-tutorial
Modular course teaching the use of napari for image visualisation and analysis


## Install napari on CAMP desktop
- Request a CAMP desktop session
- Start the CAMP desktop session
- Open xterm terminal
- run the following code in the terminal:

```
ml purge
ml Anaconda3
conda create -y -n napari-env python=3.8
conda activate napari-env
conda install napari
ml VirtualGL
vglrun napari
```

## Running napari from a Python script

Inorder to launch napari from a python script, within your script you must
import `napari` , and create the `Viewer`.

In the following code we will launch `napari` and load an image from the 
`skimage` dataset.

```python3
from skimage import data
import napari

# store the astronaut dataset from skimage
img = data.astronaut()  

# create a Viewer and add an image
viewer = napari.view_image(img)

# start the event loop and show the viewer
napari.run()
```
The napari interface will open with the astronaut image loaded:
![astronaut interface](https://napari.org/stable/_images/screenshot-add-image.png)