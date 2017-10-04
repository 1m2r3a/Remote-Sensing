## Remote Sensing: A programming guide for newbies
### Overview
Since the field of remote sensing is so wide spread but is lacking information on the programming side, I though a short blog where you can find useful information without much digging around will come in hand.

### Introduction
Remote sensing is getting information about an object without physically touching an object. Since it is a field of study we can find remote sensing in different uses from medical i.e. MRI to geography i.e. urban planning.

The main focus of remote sensing is geography which studies the satellite images or airplane. There are various satellites which can capture different wave lengths using different sensors at different resolution. In general there are two types of images captured by satellites high resolution <https://www.satimagingcorp.com/satellite-sensors/> and medium resolution <https://www.satimagingcorp.com/satellite-sensors/other-satellite-sensors/> , each type having different application.


### Landsat 
Landsat is one of the first satellite with the remote sensing scope to orbit to earth. More information and images can be obtained from their website <https://landsat.usgs.gov/>

The data is organized in a TXT file that contains information about the images like sun angle, gps coordinates, etc and each band is stored in one tif in monochrome mode/1 byte per pixel/256 bits that capture different wave length the table can be found at the following link: <https://landsat.usgs.gov/what-are-best-spectral-bands-use-my-study>

### Getting the input
One of the best website for getting the satellite images is from United States Geological Survey and can be found at <https://earthexplorer.usgs.gov/> which offers a interface similar to Google Earth

But other websites are also available like <https://search.earthdata.nasa.gov/search> or <https://scihub.copernicus.eu/dhus/#/home> a list with other data are available here <http://gisgeography.com/free-satellite-imagery-data-list/> but by searching the name of the satellite should yield the result from where you can get the data.

Depending on the chosen language the image which is stored in TIFF format can be read with various libraries: for C / C++ I've used <http://www.libtiff.org/> , for Python  <http://www.pythonware.com/products/pil/> Python Imaging Library should do the trick. After reading and storing the header of the TIFF and the data the only thing remaining is to process the pixels.

### NDVI
To compute the Normalized Difference Vegetation Index (NDVI) two TIFF images are required from the Landsat data set: Band 3 - Red	0.63 - 0.69	Discriminates vegetation slopes Band 4 - Near Infrared	0.77 - 0.90	Emphasizes biomass content and shorelines <https://www.gisresources.com/ndvi-ndbi-ndwi-ranges-1-1/>

A python guide on how to compute NDVI using python and as input Landsat image can be found at PyDataNYC2014 <https://nbviewer.jupyter.org/github/HyperionAnalytics/PyDataNYC2014/blob/master/ndvi_calculation.ipynb>

For Landsat 5 or 7 a guide that uses ArcMap and goes to the process of computing ToA if you use Level1 images can be found at <http://www.pikapartners.org/DH.php?WC=/WS/ColoradoView/TutorialsDownloads/CO_RS_Tutorial10.html>

### Output

We will end with one funky colored raster, an a use could be comparing two outputs to see how the deforestation over time evolved.

### Remote sensing

Feel free to contribute!

### Other
* <https://gist.github.com/jacquestardie/0d1c0cb413b3b9b06edf>
* <https://www.cs.uaf.edu/2007/spring/cs481/lecture/03_29_fft_image.html>
* <http://yceo.yale.edu/how-convert-landsat-dns-top-atmosphere-toa-reflectance>
