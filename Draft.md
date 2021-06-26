# Software Review for the Software PointSamplingTool

QGIS Point sampling tool, by Borys Jurgiel - a QGIS plugin, which samples polygon attributes and raster values from multiple layers at specified sampling points: https://plugins.qgis.org/plugins/pointsamplingtool/
Latest stable version: 0.5.3

## Software Metadata:

- Name: The name of the software, e.g. *"PointSamplingTool"*.
- Short description: Summary of what the software does, e.g. *"Comprehensive graphical tool for spatial data processing"*.
- Reviewed version: The software version used for the review, e.g. *"3.10.10 LTR"*.
- Platform: (Operating) systems on which the software can be used, e.g. *"Windows, MacOS, Linux, BSD, Android"*.
- Website: URL where further information can be found, e.g. *https://plugins.qgis.org/plugins/pointsamplingtool/*.
- Licensing: Software licence under which the software was published, e.g. *"Open Source with GNU General Public License (GPL)"*.
- Costs: If applicable, regular or one-off licence fees, e.g. *"free of charge"*.
- Input and output formats: The file formats the software can process, e.g. *"geodatabases" (SpatiaLite, PostGIS, MSSQL, ...), "web geodata services" (WMD/WMTS, Vector Tiles, XYZ Tiles, WFS, ...), "geo-vector data formats" (ESRI Shapefile, Geopackage, . ...), "geo-raster data formats" (GeoTIFF, ...), "table data" (CSV, TXT, ...) and other data types* (for QGIS there are an unusually large number of data formats to consider, which would go beyond the scope here).

### Use in archaeology and scientific purpose


* :bangbang:**What task is the software trying to solve?**

In archaeology, the analysis of site factors of settlements and the correlation of site evidence and geographical conditions (land use, accessibility, etc.) are questions that have been pursued with cartographic methods for about 100 years (from the viewpoint of german prehistoric research), and whose investigation can be carried out almost seamlessly with the help of Geographic Information Systems. The emergence of powerful software packages and here free opensource solutions such as QGIS have meanwhile established a kind of unspoken set of questions or surveys of geofactors that can already be expected in corresponding evaluations in the context of bachelor's degrees. In addition to the queries about the distribution of specific factors, such as soil type or land use in the vicinity of sites, settlement evidence, etc. with so-called buffers, in many cases already the query about the simplest geometric features - points - is fruitful. Here the point sampling tool serves as working horse as it aims to  facilitate the task of obtaining values of overlaying geographical features like soiltypes at the points of interest and to process them afterwards.

Elevation, slope, vegetation coverage and similar information are stored in maps, that can be digitized or - increasingly so - are generated born digital. Once the information is held in a digital way and the location of sites is held in a digital format as well, the point sampling tool can be used to transfer the relevant information from the maps to the site location, by adding them as attributes to the geometry of the points in request. The output table can be further analysed according to the archaeological question.

* :bangbang:**How does the software solve a given (technical) task?**



* :bangbang:**How does the scientific workflow implemented in the software work?**


The point sampling tool takes information from maps at specified points and adds the information to the point table. It is capable to sample several raster as well as vector maps (i.e. layers) within QGIS at the same time. 


These are the capacities which forms the major difference and advantage in comparision to the geoprocessing tools that comes by standard with QGIS (Core plugins), as they focus on either the intersection of vectorlayers or rasterlayers. 


Two of the reviewers used the tool in their research and teaching (Klammt 2015; Schmidt 20##). for this task in her master's thesis. 

<!--- * :bangbang:**Is the claim to be able to answer a certain scientific question with the chosen workflow correct?** 

The tool itself doesn't answer the scientific question, but simplifies the process of gaining information significantly. --->

* :bangbang:**Have the algorithms been implemented correctly?**

* :bangbang:**Are there any projects/application examples relevant to archaeology in which the reviewed software has already been used?**

Two of the reviewers used the tool in their research and teaching (Klammt 2015; Schmidt 20##). Both focus on gathering information regarding the geographical settings of archaeological sites and analyzing them statistically in respect to site evidence and settlement activities. Still the usage of the point sampling tool forms a necessary but hardly ramarkble part of their research routine they both omit to expand in their thesis on the tool. As the tool is probably also from other authors rarely cited, we gather here some more articles in which it could have been used: ....

Blog post: https://digital-geography.com/qgis-plugins-point-sampling-tool/

* :bangbang:**In what form is the software published?**

The software is published as a QGIS python plugin: https://plugins.qgis.org/plugins/pointsamplingtool/ 

### Usability and target group orientation

Since the Point sampling tool is a plugin, the software naturally requires the installation of the standalone QGIS software. Hardware requirements and possible limitations of QGIS itself are accordingly outside the scope of this review. 

#### Installation

* :bangbang:**How does the installation work and where is the software kept?** 

- The installation follows along the routine of the QGIS Plugin dialog. As the tool is not part of the processing toolbox, it does not align to it in the menu, but users will find them from the drop down menu of "plugins". From long lasting experience in introductionary courses on QGIS, the authors know, that this is a considerable threshold for archaeologists, who are not working constantly with QGIS but only for carrying certain tasks. Still, the sometimes for occasional user slightly confusing arrangement of the plugins in the menu is an overall usability backdrop of QGIS and not an issue of the point sampling tool.

<!---* :heavy_exclamation_mark:**Is it a stand-alone software or a web application?**

- Standalone software

<!---* :heavy_exclamation_mark:**Are necessary requirements in terms of hardware and operating system clearly documented?** 

- No, but one might infer them from QGIS --->

#### Interface

* :heavy_exclamation_mark:**Is the user interface suitable for the user group?**



* :heavy_exclamation_mark:**Is use in Archaeology intended?**

The point sampling tool is a universal helper and not specifically shaped for archaeological use.

* **Does the menu navigation follow certain de-facto standards?**

The User Interface follows the rather decent overall design and logic of the QGIS tool-dialogues (#terminologie richtig?). As that it opens up with an assistant which gives the user full control to chose not only the layer that holds as points the locations as well as the layers to be sampled, but also which attribute-values from source and sample layers should be part of the resulting new point layer. As it comes to rasters as layers this means the selection of the raster band. A second tab gives a preview of the attribute table. The third, as it is the convention for QGIS Plugins informs about the tool. Here the warning, that the tool does not align to multipoint-features, is placed relatively well. 

Here we feel that the usability offers certains thresholds. Firstly it would add to the usability, if one can include into the process also layer, that are not actively in display. Wherever granular vectordata are involved QGIS considerably slows on computers which do not apply to special requirements of lrge data proccesing. here often a good solution is to not display the data while processing them. From our experience researchers and students rely mostly on lesser powerful hardware. 
Secondly depending on the number of fields the point layers carry as well as the overlayed layers the selection of the attribute-fields quickly becomes confusing, tiring and facilitates errors. And as for example geodata on soil types often brings a quantity of attribute fields, this may concern archaeologists. A possible solution could be a partition of the dialogues between source and overlayed layers as shown by the core plugin "intersection " for the geoprocessing of vector layers. 
Thirdly the tool does not offer a temporary layer as result like (again) so many of the core plugins. Temporary layers would be an advantage when the sampling of points is a step within a workflow that aims for example to achieve the overall distribution of a position property measured on all measurement points. Here one just unnecessarily stores data, of an intermediate value.

* **Is the programme multilingual, and in which languages is it offered?**

The plugin comes in english only. 

* **Are error messages easily understandable by reviewers?**

Testing shows, that there is a warning than the user did not chose an layer to be overlayed by the point layer. However there is no warning, when a multipoint layer serves as input layer, as well there is no warning concerning possible errors caused by layers of different coordination reference systems warped together in the QGIS Project. 

#### Performance and Robustness

* **Is the implementation performant?** 

* :heavy_exclamation_mark:**Is the software robust?**

#### Help features, tutorials and community

* :bangbang:**Are there enough tutorials for learning the software?**

There are no tutorials, but as the tool is very simple and only encompasses one bais task, this is not a backdrop. It is the authors opinion, that the main source for a problematic use of this tool in archaeology lies in a lack of knowledge about the fit of spatial data granularity in archaeological investigations.

* :heavy_exclamation_mark:**Do test data sets exist for the software?**

* **Is further information on the software easy to find?**

There are several points of departure (QGIS Documentation, the QGIS plugin Manager)that leads the user to a github page of the plugin (----). Additionally the QGIS Documentation gives a thorough description of the tool and its main objective as well as a list of the versions history.  

<!--- * :bangbang:**Is the software supported by a community, and what proportion are classical and ancient studies scholars?** -->


* :heavy_exclamation_mark:**Are there archaeological best practices or publications that refer to the reviewed software?**

No, but this won't make any sense, still there are trillions of idiotic "studies" that may made use of the tool. But you can't blame the plate for the disgusting food it serves.

#### Data ingest, interoperability and programming interfaces

* :bangbang:**Which data formats are read in and how?**

- Every dataformat supported in QGIS. Still matching the task it is supposed to perform, only point feature (no multipoints) can serve as input layers.   

* :bangbang:**Which output data formats are supported?**

The results of the process are outputed as Geopackage (dgpk) by default, csv and shapefile are as well offered.

* :heavy_exclamation_mark:**How can data be read in? Does the software allow batch processing?**

The QGIS plugin does not offer a batch process. The input data and the parameters have to be manually chosen via the GUI. As stated in the context of the usability of the GUI this is a backdrop.


* :bangbang:**Is there an application programming interface (API)?**



#### Conformity with regulations on data protection and data minimisation

* **Does the software comply with the laws (e.g. on data protection, map displays, etc.) of the country of assignment?**

* **What data does the application store, for what purpose and for how long? Are data transferred to third parties?**

### Developer perspective

#### Documentation and tests

* **Does a source code documentation exist and, if applicable, is an HTML variant of it available?**

* **Is the build process documented and, if applicable, automated by means of build scripts?**

* :heavy_exclamation_mark:**Is the documentation up to date and does it address all functions of the programme?**

* **Is there developer documentation that promotes further software development?**

* **Does the source code contain software tests for testing core functions and demonstrating them to other developers?**

* **Is it made easy for the developer to test the software (e.g. virtual machine, Docker container, installer)?**

* **Are the developers readily accessible?**

* :heavy_exclamation_mark:**Is the software being actively worked on?**

* :bangbang:**Is it possible to support software development?**

#### Quality of implementation

* **Does the implementation reflect the state of the art?** 

* **Is *Continuous Integration* used to ensure implementation quality?**


