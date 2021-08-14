# Tweaker-3
## The Tweaker is an auto-rotate module which finds the STL or 3MF object's optimal orientation on the printing platform to improve the efficiency of 3D printing.

![Auto-rotation of a model](https://github.com/ChristophSchranz/Tweaker-3/blob/master/auto-rotation.png)
Author: Christoph Schranz, 12.01.2016 

[Salzburg Research](http://www.salzburgresearch.at/blog/3d-print-positioning/)

## Quickstart:  

`python Tweaker.py -i demo_object.stl -vb`

If you want to install this module as a CLI package install it via `pip`:

    pip install git+https://github.com/ChristophSchranz/Tweaker-3.git

### Extended mode:

This mode yields the most reliable results, 
but needs slightly more computation time. 
This is the suggested mode.

`python Tweaker.py -i death_star.stl -vb -x`


### Minimise the necessary support material:

If you want to optimise the print in terms of minimal support surfaces
 instead of the default volume, add the parameter `-min sur` 
 or `--minimize surfaces`

`python Tweaker.py -i demo_object.stl -min sur -x`



### Convert a 3mf object to stl without tweaking:

`python Tweaker.py -i pyramid.3mf -c  -o pyramid.stl`


### Choose the output type of the STL format:

`python Tweaker.py -i pyramid.3mf -t asciistl`

You can choose the output types "asciistl" and 
"binarystl" (default). "3mf" is not supported yet.


### Just see the results:

`python Tweaker.py -i demo_object.stl -r`


### Show the progress of tweaking:

`python Tweaker.py -i demo_object.stl -x -p`



### Favour Side:

In some cases the surface of one side of an object  
may be more important than those of the others. 
Therefore, a selected orientation (and all close ones in terms of a small scalar product) 
can be weighted by using the flag `--favside (fs)` Here is an example 
of how to favour facets in the direction `x=1, y=-1.0, z=2.5` with a weighting factor 
of `3.0`:

`python Tweaker.py -i demo_object.stl -vb -x -fs "[[0,-1,2.5],3.0]"`


### Find Help:

`python Tweaker.py -h`

### Version:

`python Tweaker.py -v`


## Further Repos:

### Previous Version

The Tweaker's initial repository is here:

<a href="https://github.com/iot-salzburg/STL-tweaker">
  <img align="center" src="https://github-readme-stats.vercel.app/api/pin/?username=iot-salzburg&repo=STL-Tweaker&theme=slateorange" />
</a>


### Ultimaker Cura 2, 3 and 4 - Plugin

The **Tweaker-3** is available in [Cura](https://ultimaker.com/software/ultimaker-cura) 
as **Auto-Orientation** in the *Marketplace* (Cura >= 4) respectively 
the *plugin manager*. 

<a href="https://github.com/nallath/CuraOrientationPlugin">
  <img align="center" src="https://github-readme-stats.vercel.app/api/pin/?username=nallath&repo=CuraOrientationPlugin&theme=slateorange" />
</a>


### OctoPrint - Plugin

The **Tweaker-3** is available as **PrePrint-Service** in [OctoPrint](https://octoprint.org/) 
and can be installed as described in this 
[instruction](https://plugins.octoprint.org/plugins/preprintservice/). 
Note that this module combines the auto-rotation functionality with slicing in an external Docker service.

<a href="https://github.com/ChristophSchranz/Octoprint-PrePrintService">
  <img align="center" src="https://github-readme-stats.vercel.app/api/pin/?username=christophschranz&repo=Octoprint-PrePrintService&theme=slateorange" />
</a>

### Webservice

Another way to test the functionality of the **Tweaker-3** is the usage of a Docker-based web service
as described in the repository [PrePrintService](https://github.com/ChristophSchranz/Pre-Print-Service).

<a href="https://github.com/ChristophSchranz/PrePrintService">
  <img align="center" src="https://github-readme-stats.vercel.app/api/pin/?username=christophschranz&repo=Pre-Print-Service&theme=slateorange" />
</a>


## Interested in how the algorithm works?

This [Whitepaper](https://www.researchgate.net/publication/311765131_Tweaker_-_Auto_Rotation_Module_for_FDM_3D_Printing) 
declares this program. Additionally, background 
infos and benchmarks are provided.

## Donation

Most of this code was developed in my spare time to provide a performant auto-rotation module to the open-source 3D printing community.
If you like this project or it helps you to reduce time to develop, I would be very thankful about a cup of coffee :) 

[![More coffee, more code](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=RG7UBJMUNLMHN&source=url)
