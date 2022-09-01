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
