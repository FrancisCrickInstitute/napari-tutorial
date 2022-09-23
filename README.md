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
After running the previous code you should then see the following blank interface:

![napari blank interface](https://raw.githubusercontent.com/FrancisCrickInstitute/napari-tutorial/main/images/blank_napari_interface.png?token=GHSAT0AAAAAABXXRCUATCFRQ6STP36JA2QYYZN5HAA)
The following will go into more detail about each element of the interface.
![](https://raw.githubusercontent.com/FrancisCrickInstitute/napari-tutorial/main/images/blank_napari_interface_labels.png?token=GHSAT0AAAAAABXXRCUBCM7ULAN2FAIAWOWSYZN32XQ)

1. **New Points Layer** - This will create a new `napari` `Points` and add it to the `Viewer`. The `Points` layer allows 
you to display an `NxD` array of `N` points in `D` coordinates. More info [here](https://napari.org/stable/howtos/layers/points.html).
2. **New Shape Layer** - This will create a new `napari` `Shapes` and add it to the `Viewer`. The `Shapes`
layer allows you to display a list of `NxD` arrays, where each array corresponds to one shape. More info [here](https://napari.org/stable/howtos/layers/shapes.html).
3. **New Labels Layer** - This will create a new `napari` `Labels` layer and add it to the `Viewer`. The `Labels` layer
allows you to take an array of integers and display each integer as a different random color with the background color
0 rendered as transparent. More info [here](https://napari.org/stable/howtos/layers/labels.html).
4. **Delete Selected Layer** - This will delete a selected layer from the `Viewer`.
5. **Show/Hide IPython Console** - The built-in IPython console will allow you to programmatically interact with the viewer.
6. **Toggle ndisplay** - This will change the `Viewer` to view any visible layers in three-dimensions.
7. **Change order of the visible axis** - This will transpose a layer across all of its axis.
8. **Transpose order of the last two visible axis** - This will transpose a layer only across its last two visible axis.
9. **Toggle grid mode** - This will change the layout of the `Viewer` to show all layers in a grid layout.
10. Reset viewer to original state - This will reset the `Viewer` to show a layer in its original state.
## Running napari from a Python script

Inorder to launch napari from a python script, within your script you must
import `napari` , and create the `Viewer`.

In the following code we will launch `napari` and load an image from 
`skimage.data`.

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
The napari interface will then open with the astronaut image loaded:
![napari astronaut interface](https://napari.org/stable/_images/screenshot-add-image.png)

To open an image stored locally in `napari` using a python script you 
must first read in your image, add it to the `Viewer` and then run `napari`.

To read in an image we can use the `skimage.io` `imread` function.

Like before 

```python
from skimage.io import imread
import napari

# reading image from path
img = imread("/path/to/image")

viewer = napari.view_image(img)

napari.run()
```



