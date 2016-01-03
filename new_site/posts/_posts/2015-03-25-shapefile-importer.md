---
layout: blog
type: blog
title: Shapefile Importer GUI for PGAdmin3 (for mac)
---
I had been struggling to add the Shapefile importer tool to PGAdmin3 for a PostGIS database we're working on in my class but I figured out an alternative! <em>As an aside, the shp2pgsql command line is totally great &amp; amazing, but I wanted to have a GUI for when I want to be extra careful.</em>

I downloaded the <a href="http://boundlessgeo.com/solutions/opengeo-suite/" target="_blank">OpenGeoSuite</a> from Boundless Geo and if you have the postgres.app and pgAdmin3 installed (which is the setup I definitely recommend for Mac), when you open the geosuite, you can click on the utilities:

Which shows this:

![pgadmin 1](../../../../assets/img/blog/pgadmin.png)

![pgadmin 2](../../../../assets/img/blog/pgadmin2.png)

The pgShapeLoader should be pulled in your applications folder and ta da! it's installed.

<span style="text-decoration: underline;"><strong>Now How Do I Use This Thing?!</strong></span>
Open the ShapeLoader to set up your connection details, which if you're unsure about, can be copied almost word for word from PGAdmin3.

![pgadmin 3](../../../../assets/img/blog/pgadmin3.png)

Then click add files...

![pgadmin 4](../../../../assets/img/blog/pgadmin4.png)

After adding the file you can edit the SRID, the Geo Column, etc.

I've had no problem with this at all, but if it doesn't work I recommend just using the command line.

QGIS has an option for this of course built in through their SPIT tool (and has a bunch of great data management tools in general that I'll explain in the future)