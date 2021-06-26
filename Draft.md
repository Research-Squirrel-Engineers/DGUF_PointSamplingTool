# Software Review for the Software PointSamplingTool


## Software Metadata:

- Name: The name of the software, e.g. *"PointSamplingTool"*.
- Short description: Summary of what the software does, e.g. *"Comprehensive graphical tool for spatial data processing"*.
- Reviewed version: The software version used for the review, e.g. *"3.10.10 LTR"*.
- Platform: (Operating) systems on which the software can be used, e.g. *"Windows, MacOS, Linux, BSD, Android"*.
- Website: URL where further information can be found, e.g. *https://qgis.org*.
- Licensing: Software licence under which the software was published, e.g. *"Open Source with GNU General Public License (GPL)"*.
- Costs: If applicable, regular or one-off licence fees, e.g. *"free of charge"*.
- Input and output formats: The file formats the software can process, e.g. *"geodatabases" (SpatiaLite, PostGIS, MSSQL, ...), "web geodata services" (WMD/WMTS, Vector Tiles, XYZ Tiles, WFS, ...), "geo-vector data formats" (ESRI Shapefile, Geopackage, . ...), "geo-raster data formats" (GeoTIFF, ...), "table data" (CSV, TXT, ...) and other data types* (for QGIS there are an unusually large number of data formats to consider, which would go beyond the scope here).

### Use in archaeology and scientific purpose


* :bangbang:**What task is the software trying to solve?**

In archaeology, the analysis of site factors of settlements and the correlation of site evidence and geographical conditions (land use, accessibility, etc.) are questions that have been pursued with cartographic methods for about 100 years (from the viewpoint of german prehistoric research), and whose investigation can be carried out almost seamlessly with the help of Geographic Information Systems. The emergence of powerful software packages and here free opensource solutions such as QGIS have meanwhile established a kind of unspoken set of questions or surveys of geofactors that can already be expected in corresponding evaluations in the context of bachelor's degrees. In addition to the queries about the distribution of specific factors, such as soil type or land use in the vicinity of sites, settlement evidence, etc. with so-called buffers, in many cases already the query about the simplest geometric features - points - is fruitful. Here the point sampling tool serves as working horse as it aims to  facilitate the task of obtaining values of overlaying geographical features like soiltypes at the points of interest and to process them afterwards.

Elevation, slope, vegetation coverage and similar information are stored in maps, that can be digitized or - increasingly so - are generated born digital. Once the information is held in a digital way and the location of sites is held in a digital format as well, the point sampling tool can be used to transfer the relevant information from the maps to the site location, by adding them as attributes to the geometry of the points in request. The output table can be further analysed according to the archaeological question.

* :bangbang:**How does the software solve a given (technical) task?**

* :bangbang:**How does the scientific workflow implemented in the software work?**


The point sampling tool takes information from maps at specified points and adds the information to the point table. It can be used to sample several raster as well as vector maps (i.e. layers) within QGIS at the same time. 


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



#### Installation

* :bangbang:**How does the installation work and where is the software kept?** 

- Installation using the QGIS Plugin dialog

* :heavy_exclamation_mark:**Is it a stand-alone software or a web application?**

- Standalone software

* :heavy_exclamation_mark:**Are necessary requirements in terms of hardware and operating system clearly documented?**

- No, but one might infer them from QGIS

#### Interface

* :heavy_exclamation_mark:**Is the user interface suitable for the user group?**

* :heavy_exclamation_mark:**Is use in Archaeology intended?**

* **Does the menu navigation follow certain de-facto standards?**

* **Is the programme multilingual, and in which languages is it offered?**

* **Are error messages easily understandable by reviewers?**

#### Performance and Robustness

* **Is the implementation performant?** 

* :heavy_exclamation_mark:**Is the software robust?**

#### Help features, tutorials and community

* :bangbang:**Are there enough tutorials for learning the software?**

* :heavy_exclamation_mark:**Do test data sets exist for the software?**

* **Is further information on the software easy to find?**

* :bangbang:**Is the software supported by a community, and what proportion are classical and ancient studies scholars?**

* :heavy_exclamation_mark:**Are there archaeological best practices or publications that refer to the reviewed software?**

#### Data ingest, interoperability and programming interfaces

* :bangbang:**Which data formats are read in and how?**

- Every dataformat supported in QGIS

* :bangbang:**Which output data formats are supported?**

- Every dataformat supported in QGIS

* :heavy_exclamation_mark:**How can data be read in? Does the software allow batch processing?**

- Using QGIS

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


