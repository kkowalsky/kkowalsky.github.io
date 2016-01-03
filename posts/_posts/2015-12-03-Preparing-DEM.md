---
layout: blog
type: blog
title: Preparing Your DEM
---
Edit: Daniel Huffman pointed out to me a common problem that might happen if you assign 16 bit unsigned right away. I've edited the blog to show where you should assign the pixel type to avoid stairstepping problems that might occur.

This semester I've been able to work with terrain maps, which has always been a part of cartography I've been afraid to do. The amount of unfamiliar terms and processes can be scary while following along with one of <a href="http://shadedrelief.com/" target="_blank">Tom Patterson's </a> tutorials or just trying to get a DEM ready for using in Blender, following Daniel Huffman's <a href="https://somethingaboutmaps.wordpress.com/2014/01/01/blender-tutorial/" target="_blank">3-d modeling technique</a>. This blog attempts to talk about the geoprocessing required in ArcGIS (If you know how to do this in QGIS, please let me know!) for getting a DEM ready for making beautiful terrain maps in Blender (think of this as a prequel to Daniel's video series).

Step One:

Don't know where to get DEM data to begin with? I recommend using <a href="http://www.viewfinderpanoramas.org/Coverage%20map%20viewfinderpanoramas_org3.htm" target="_blank">Viewfinder Panorama</a> to download 3" DEM from their global coverage map. I could make a separate blog post on comparing the differences of websites for downloading DEMs, but this one is simple stupid (which is probably why I use it). Just click on the area you want and download it.

Step Two:

Once you've unzipped the folder, create a ArcCatalog connection to the folder and load one of the images into ArcGIS. These DEMs are in .hgt files that as you can see, which is a file type used by NASA for the Shuttle Radar Topography Mission that collects radar data (all you need to know is that it loads into ArcGIS no problem). You may notice that the image might only cover a small portion of the area you're trying to make shaded relief for. We'll fix that problem in a bit, but for right now just load in all the images you need. To figure out how many of these images you need, it helps to add some of the vector data you're going to use for admin0 or admin1 boundaries from <a href="http://naturalearthdata.com/downloads/" target="_blank">Natural Earth</a> to give you a sense of what additional DEM images you have to add.

Step Three:

Now that you have all the DEM images loaded into ArcGIS, its time to combine them! This is where we create what's called a Mosaic Dataset. The first step is to create a new file geodatabase on the ArcCatalog tab in the same place you're data is stored. Make sure you make this the default geodatabase so you don't have to constantly redirect to it. Then right click on the new database and select 'New' and press 'Mosaic Dataset'

![dem 1](../../../../assets/img/blog/dem1.png)

Once you do that, you'll be shown the menu below:

![dem 2](../../../../assets/img/blog/dem2.png)

Make sure you name the dataset and set a coordinate system. Once you press 'Ok', you'll see an empty mosaic added in your table of contents and a new mosaic dataset in ArcCatalog.

Step Four:

Once you've created a mosaic dataset, you have to put in the DEMs you want to be stitched together. To do that, right click on the mosaic dataset in the ArcCatalog and select 'Add Rasters'. This will bring you to a menu where you can select your .hgt files. Select all of the images you want to include and then there a couple of checkboxes to press to prevent the mosaic from not working.

![dem 3](../../../../assets/img/blog/dem3.png)

First check the 'Update Overviews' checkbox under the regular set of options. Then open 'Advanced Options' and check 'Build Raster Pyramids', 'Calculate Statistics', and 'Build Thumbnails'. Once they load, you should be able to seem your DEMs all stitched together.

Step Five:

Now that your mosaic dataset is done, I recommend importing all of the vector data you want to include to keep in your .mxd file. It's not required in order to get into Blender, but can be time consuming to add everything in later.

Step Six:

Right click on the image in your mosaic dataset in 'Table of Contents' and export the DEM as an image (I recommend as a TIFF). Then add the layer to the map.

Step Seven:

Open the 'Extensions' button under 'Customize' on the main menu and make sure to select the 'Spatial Analyst' extension. Then search for the 'Raster calculator' tool. Your DEM has a range of values from 0 to 1000 typically and the full range of values actually extends from 0 to 65,000. In order to have Blender see the full range of values, you're going to want to multiply by a number that gets the max to 65,000. If you have negative numbers, this is also the time to get rid of that (as Blender won't be able to use that value).

Step Eight:

Use the ArcGIS tool 'Copy Raster' to create a new version of this mosaic with a '16 bit unsigned' pixel type.

Step Nine:

Once you've edited the range of your DEM's values, export the layer as a TIFF.

Last step:

Whooo! You have a TIFF exported and ready to put into Blender, right? WRONG. Turns out, ArcGIS messes with TIFFs on export so when you load the terrain into Blender, this is what it looks like:

![dem 4](../../../../assets/img/blog/dem4.png)

To solve this terrible problem, the (hopefully) only step required is to open the DEM.tif in Photoshop and 'Save As' a new tiff (DEM2.tif for instance). This will clean out any junk left from the export from ArcGIS and allow you to easily import to make beautiful terrain in Blender!!