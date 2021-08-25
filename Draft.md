---
title: Software Review PointSamplingTool / Software Review PointSamplingTool

layout: draft
author:
  -
    name: Timo Homburg
    affiliation: Hochschule Mainz
    orcid: 0000-0002-9499-5840
    bio: "Timo Homburg studierte Informatik mit den Schwerpunkten Computerlinguistik (Assyrologie), Semantic Web und Sinologie. In den letzten Jahren arbeitete er im Bereich der GIS-Anwendungen in der Geoinformatik. Seine Doktorarbeit beschäftigt sich mit der besseren Integration von Geodaten in ein Semantic-Web-Umfeld. Sein aktuelles Forschungsvorhaben beschäftigt sich mit der Schaffung digitaler Standards im Bereich Assyrologie und der Best-Practice-Dokumentation von Ausgrabungen mit Keilschrifttexten – eine Erweiterung seiner Publikationen zum Thema ‚Keilschrift in den Digital Humanities‘."
  -
    name: Anne Klammt
    affiliation: Deutsches Forum für Kunstgeschichte Paris
    orcid: 0000-0003-3697-9241
    bio: "Die Archäologin Anne Klammt hat über ein landschaftsarchäologisches Thema promoviert und ist seit 2020 als Forschungsleiterin für die Weiterentwicklung der Digitalen Kunstgeschichte am Deutschen Forum für Kunstgeschichte Paris verantwortlich."
  -
    name: Sophie Charlotte Schmidt
    affiliation: Deutsches Archäologisches Institut
    orcid: 0000-0003-4696-2101
    bio: "Sophie C. Schmidt studierte Altertumswissenschaften und Prähistorische Archäologie an der Freien Universität Berlin. Im Anschluss arbeitete sie als Wissenschaftliche Mitarbeiterin im Bereich Archäoinformatik an den Universitäten Köln und Bonn, derzeit ist sie bei dem Konsortialprojekt NFDI4Objects am Deutschen Archäologischen Institut beschäftigt."
  -
    name: Florian Thiery
    affiliation: Römisch-Germanisches Zentralmuseum – Leibniz-Forschungsinstitut für Archäologie
    orcid: 0000-0002-3246-3531
    bio: "Florian Thiery ist studierter Geodät und Research Software Engineer (RSE) im Arbeitsbereich *Wissenschaftliche IT, Digitale Plattformen und Tools* am Römisch-Germanischen Zentralmuseum in Mainz. Er ist Initiator der *Research Squirrel Engineers*, einem Netzwerk für RSEs in den Digital Humanities und Communityprojekte mit Fokus auf freie und offene Daten, sowie Linked Open Data. Im Rahmen eines Stipendiums des *Wikimedia Fellow-Programm Freies Wissen* beschäftigt er sich mit der Modellierung von irischen ᚑᚌᚆᚐᚋ (Ogham) Steinen und deren Publikation im Wikimedia Universum."

bibliography: bibliography.bib
keywords:
  - Archäologie
  - PointSamplingTool
  - Softwarebewertung
  - Forschungssoftware
  - Rezension
keywords_en:
  - archaeology
  - manual
  - software review
  - research software
  - review
---

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

In archaeology, the analysis of site factors of settlements and the correlation of sites and geographic conditions (land use, accessibility, etc.) are questions that have been pursued with cartographic methods for about 100 years (from the perspective of German prehistoric research) and whose investigation can be carried out almost seamlessly with the help of Geographic Information Systems. With the advent of powerful software packages and here free open source solutions such as QGIS, a kind of unspoken questionnaire or survey of geofactors has now become established, which can already be expected in corresponding evaluations in the context of bachelor theses. In addition to queries for the distribution of certain factors, such as soil type or land use in the vicinity of sites, settlement evidence, etc. with so-called buffers, in many cases already the query for the simplest geometric features - points - is fruitful. Here, the Point Sampling Tool serves as a workhorse, as it is designed to facilitate the task of obtaining values of overlying geographic features such as soil types at points of interest.

Elevation, slope, vegetation coverage and similar information are stored in maps, that can be digitized or - increasingly so - are generated born digital. Once the information is held in a digital way and the location of sites is held in a digital format as well, the point sampling tool can be used to transfer the relevant information from the maps to the site location, by adding them as attributes to the geometry of the points in request. The output table can be further analysed according to the archaeological question.

* :bangbang:**How does the software solve a given (technical) task?**



* :bangbang:**How does the scientific workflow implemented in the software work?**

The Python-based Point Sampling Tool extracts information from maps at specific points and adds this information to the point table. It is capable of sampling both multiple raster and vector maps (i.e. layers) within QGIS simultaneously. In doing so, it follows a routine that addresses the vector layers first and then the raster data (if both data types are included at the same time). This process sequence also determines the arrangement of the attribute fields. 

For multiband raster data the user has to decide which bands he wishes to sample (several bands at once are possible). For vector the attributes have to be selected - again it is possible to include all attributes. The number of resulting records is identical to the number of input points and for each vectorlayer only one geometry (feature) is taken into account, that is the last one in the processing, i.e. the onewith the highest id. Therefore the point sampling tool can not be used for obtaining complete and fully controlled values form vectorlayers with several overlaying geometries. Taht latter could for example be the case for layers with overlaying buffers of sites or geographical feature that partly overlay each other.


Two of the reviewers used the tool in their research and teaching (Klammt 2015; Schmidt 20##). for this task in her master's thesis. 

<!--- * :bangbang:**Is the claim to be able to answer a certain scientific question with the chosen workflow correct?** 

The tool itself doesn't answer the scientific question, but simplifies the process of gaining information significantly. --->

* :bangbang:**Have the algorithms been implemented correctly?**

Ja.

* :bangbang:**Are there any projects/application examples relevant to archaeology in which the reviewed software has already been used?**

Two of the reviewers used the tool in their research and teaching (Klammt 2015; Schmidt 20##). Both focus on gathering information regarding the geographical settings of archaeological sites and analyzing them statistically in respect to site evidence and settlement activities. Still the usage of the point sampling tool forms a necessary but hardly remarkble part of their research routine they both omit to expand in their thesis on the tool. As the tool is probably also from other authors rarely cited, we gather here some more articles in which it could have been used: ....

Blog post: https://digital-geography.com/qgis-plugins-point-sampling-tool/

* :bangbang:**In what form is the software published?**

The software is published as a QGIS python plugin: https://plugins.qgis.org/plugins/pointsamplingtool/ 

### Usability and target group orientation

Since the Point sampling tool is a plugin, the software naturally requires the installation of the standalone QGIS software. Hardware requirements and possible limitations of QGIS itself are accordingly outside the scope of this review. 

#### Installation

* :bangbang:**How does the installation work and where is the software kept?** 

- The installation follows along the routine of the QGIS Plugin dialog. As the tool is not part of the geo processing toolbox, it does not align to it in the menu, but users will find it from the drop down menu of "plugins". From long lasting experience in introductionary courses on QGIS, the authors underline, that this is a considerable threshold for archaeologists, who are not working constantly with QGIS but only occasionally for carrying certain tasks. Still, the sometimes for those users slightly confusing arrangement of the plugins in the menu is an overall usability backdrop of QGIS and not an issue that the point sampling tool is to blame for.

<!---* :heavy_exclamation_mark:**Is it a stand-alone software or a web application?**

- Standalone software

<!---* :heavy_exclamation_mark:**Are necessary requirements in terms of hardware and operating system clearly documented?** 

- No, but one might infer them from QGIS --->

#### Interface

* :heavy_exclamation_mark:**Is the user interface suitable for the user group?**



* :heavy_exclamation_mark:**Is use in Archaeology intended?**

The point sampling tool is a universal helper and not specifically shaped for archaeological use.

* **Does the menu navigation follow certain de-facto standards?**

The Graphical User Interface follows the rather decent overall design and logic of the QGIS tool dialogues. As that it opens up with an assistant that gives the user full control to chose the layer that holds as points the locations as well as the layers to be sampled. Furthermore the user has to indicate which attribute-values from the source and the sample layer(s) should be part of the resulting new point layer. As it comes to raster data this means the selection of the raster band. A second tab gives a preview of the attribute table. The third, as it is the convention for QGIS Plugins, informs about the tool. Here the warning, that the tool does not align to multipoint-features, is placed relatively well. There is however no logfile, that facilitates the documentation and by that the reproducibility.

Here we feel that the usability offers certain thresholds. Firstly it would add to the usability, if one can include into the process also layers, which are not actively in display. Wherever granular vectordata are involved QGIS considerably slows on computers which do not apply to special requirements of large data proccesing. Here often a workaround is to not display the data while processing them. From our experience researchers and students rely mostly on lesser powerful hardware. 

Secondly depending on the number of fields the input point layer carrys as well as the overlayed layers the selection of the attribute-fields quickly becomes confusing, tiring and facilitates errors. And as for example geodata on soil types often brings a quantity of attribute fields, this may concern archaeologists. A possible solution could be a partition of the dialogues between source and overlayed layers as shown by the core plugin "intersection " for the geoprocessing of vector layers. 

Thirdly the tool does not allow identical field names for the resulting point layer, as this would indeed complicate or even prevent the user to interprete the resulting layer correctly. Luckily enough the tool offers a way to rename the fields before on the fly before starting the process. Still the renaming is restricted by the maximal length of 10 chars - longer entries get truncated. In the reviewers experience this complicates matters in so far, as in combination of the lack of a logfile the comprehensibilty of the resulting files is  affected by this.

Finally the tool does not offer a temporary layer as result like (again) so many of the core plugins. Temporary layers would be an advantage when the sampling of points is a step within a workflow that aims for example to achieve the overall distribution of a position property measured on all measurement points. Here one just unnecessarily stores data, of an intermediate value.

* **Is the programme multilingual, and in which languages is it offered?**

The plugin comes in english only. 

* **Are error messages easily understandable by reviewers?**

Testing shows, that there are error messages as well as warnings. Errors encompasses wrong or missing choices concerning the layers to be matched or identical fieldnames. A warning is given when layers of different coordination reference systems are concerned. As it is warning you can overreide this, that allows seemless working with data that might have false metadata. And short phrases as status support the user in solving errors and problems.

#### Performance and Robustness

* **Is the implementation performant?** 

The point-sampling-tools is integrating seamless into the QGIS environment.

* :heavy_exclamation_mark:**Is the software robust?**

Habe Punktelayer mit 16000 Punkten auf Bufferlayer mit umfanreichen geometrischen Überlagerungen getestet. Lief problemlos und un din wenige rals einer Minute.

#### Help features, tutorials and community

* :bangbang:**Are there enough tutorials for learning the software?**

There are no tutorials offered by QGIS itself (Documentation?), but according to the wide use of the tool, indicated by the sheer number of downloads) there are tutorials from users, teachers and university courses on the internet. This is especially helpful, as they come in a variety of languages like French, Spanish and Portugese, so its use in an international context with multilingual research teams is facilitated.

* :heavy_exclamation_mark:**Do test data sets exist for the software?**

I don't think so 

* **Is further information on the software easy to find?**

There are several points of departure (QGIS Documentation, the QGIS plugin repository  that leads the user to the code repository of the plugin at github ([https://github.com/borysiasty/pointsamplingtool](https://github.com/borysiasty/pointsamplingtool). Additionally the [QGIS Plugin repository](https://plugins.qgis.org/plugins/) gives a thorough description of the tool and its main objectives as well as a list of the versions history ([Point sampling tool](https://plugins.qgis.org/plugins/pointsamplingtool/)).  

<!--- * :bangbang:**Is the software supported by a community, and what proportion are classical and ancient studies scholars?** -->


* :heavy_exclamation_mark:**Are there archaeological best practices or publications that refer to the reviewed software?**

No, but this won't make any sense in respect to the task the tool carries out.

#### Data ingest, interoperability and programming interfaces

* :bangbang:**Which data formats are read in and how?**

- Every dataformat supported in QGIS. Still, matching the task it is supposed to perform, only point feature (no multipoints) can serve as input layers.   

* :bangbang:**Which output data formats are supported?**

The results of the process are outputed as Geopackage (dgpk) by default, csv and shapefile are as well offered.

* :heavy_exclamation_mark:**How can data be read in? Does the software allow batch processing?**

The QGIS plugin does not offer a batch process. The input data and the parameters have to be manually chosen via the GUI. As stated in the context of the usability of the GUI this is a backdrop.


* :bangbang:**Is there an application programming interface (API)?**
The plugin support the QGIS processing API, which allows this plugin to be integrated into other QGIS (batch) proccessing tasks. 


<!--- >#### Conformity with regulations on data protection and data minimisation

* **Does the software comply with the laws (e.g. on data protection, map displays, etc.) of the country of assignment?**

* **What data does the application store, for what purpose and for how long? Are data transferred to third parties?** -->

### Developer perspective

The source code of the PointSamplingTool is publicly available on Github and the software is liecense under the terms of the GNU GPL.

#### Documentation and tests

* **Does a source code documentation exist and, if applicable, is an HTML variant of it available?**
The python script does not include a HTML documentation, but contains numerous comments in the available source code. Even though it would be advisable to create a HTML documentation that is appropriate for Python, one has to take into account the scope of the QGIS plugin and its frame of reference. A QGIS plugin contains certain fixed structures which should be obvious to anyone developing a QGIS plugin. The source code is also comparatively limited and can be assessed by the average developer without too much effort.

* **Is the build process documented and, if applicable, automated by means of build scripts?**
  The build process is not documented, but in this case this is also not necessary, as a QGIS plugin only needs to be extracted into the QGIS plugin folder.

* :heavy_exclamation_mark:**Is the documentation up to date and does it address all functions of the programme?**
  No source code 

* **Is there developer documentation that promotes further software development?**

I don't think so. But: der code ist kommentiert und dort finden sich auch Hinweise des Entwicklers auf bestehende Probleme, die er bislang nicht lösen konnte ->  https://github.com/borysiasty/pointsamplingtool/blob/master/doPointSamplingTool.py Zeile 206 folgende

* **Does the source code contain software tests for testing core functions and demonstrating them to other developers?**
 The source code does not provide software tests and no example data or any other hints as to how the software can be tested. The software repository might benefit from a small tutorial with some sample data, such as the ones we contribute with our software review article.

* **Is it made easy for the developer to test the software (e.g. virtual machine, Docker container, installer)?**
  Yes. The user is able to install the plugin from within QGIS by just selecting the latest version in the QGIS plugin dialogue.

* **Are the developers readily accessible?**
  Judging from the Github issues and pull requests from the project, the authors gets the impression that there are not many issues and pull requests, but the ones that have been raised have always been addressed by the main developer.

* :heavy_exclamation_mark:**Is the software being actively worked on?**

From the perspective of the reviewers the software is activley maintained by almost entirely one developer. Pull requests are open but the problems solved or otherwise commented. 

* :bangbang:**Is it possible to support software development?**
 The software development can be supported and has been supported, as proven by a number of accepted pull requests in the Github repository. However, the developed does not give a guideline as to how he expects contributions to be submitted (contribution guideline). The developer also does not describe a roadmap of a goals as to which functions might be implemented in later versions. This might give other developers an orientation as to which contributions might be useful to make. However, one might argue that the developer might consider his work to be finished or the tool sufficiently apt for use in QGIS. In that case, there are possibly no future plans apart from maintaining the software.

#### Quality of implementation

* **Does the implementation reflect the state of the art?** 

* **Is *Continuous Integration* used to ensure implementation quality?**


