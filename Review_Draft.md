# Software Review for the Software PointSamplingTool

QGIS Point sampling tool, by Borys Jurgiel - a QGIS plugin, which samples polygon attributes and raster values from multiple layers at specified sampling points: https://plugins.qgis.org/plugins/pointsamplingtool/
Latest stable version: 0.5.3

## Software Metadata:

- Name: *PointSamplingTool*.
- Short description: *QGIS plugin for sampling polygon attributes and raster values from multiple layers at specified sampling points*.
- Reviewed version: *0.5.3*.
- Platform: *Windows, MacOS, Linux*.
- Website: *https://plugins.qgis.org/plugins/pointsamplingtool/*.
- Licensing: *"Open Source with GNU General Public License (GPL)"*.
- Costs: *free of charge*.
- Input and output formats: *geo-vector data formats (ESRI Shapefile, Geopackage, . ...), geo-raster data formats (GeoTIFF, ...), "table data" (CSV, TXT, ...)* .

### Use in archaeology and scientific purpose

In archaeology, the analysis of site factors of settlements and the correlation of sites and geographic conditions (land use, elevation, slope, accessibility, etc.) are questions that have been pursued with cartographic methods for more than 100 years [@grunwald_2016]. These investigations can nowadays be carried out almost seamlessly with the help of Geographic Information Systems. In addition to queries for the distribution of certain factors, such as soil type or land use in the vicinity of sites, settlement evidence, etc. with so-called buffers, in many cases already the query for the simplest geometric features - points - is fruitful. Here, the Point Sampling Tool serves as a workhorse, as it is designed to facilitate the task of obtaining values of overlying geographic features such as soil types at points of interest: The geographic information of interest are stored in maps, that can be digitized or - increasingly so - are generated born digital. Once the information is held in a digital way and the location of sites is held in a digital format as well, the QGIS point sampling tool can be used to transfer the relevant information from the maps to the site location, by adding them as attributes to the geometry of the points in request. The output table can then be further analysed according to the archaeological question.

#### Workflow of the QGIS Point Sampling Tool

The Python-based Point Sampling Tool extracts information from maps at points specified by a point layer and adds this information to the attribute table of the points. It is capable of sampling both multiple raster and vector maps (i.e. layers) within QGIS simultaneously. In doing so, it follows a routine that addresses the vector layers first and then the raster data (if both data types are included at the same time). This process sequence also determines the arrangement of the attribute fields. 

For multiband raster data the user has to decide which bands he wishes to sample (several bands at once are possible). For vector the attributes have to be selected - again it is possible to include all attributes. The number of resulting records is identical to the number of input points and for each vector layer only one geometry (feature) is taken into account, that is the last one in the processing, i.e. the one with the highest id. Therefore the point sampling tool can not be used for obtaining complete and fully controlled values form vector layers with several overlaying geometries. The latter could for example be the case for layers with overlaying buffers of sites or geographical feature that partly overlay each other.


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

From the perspective of a developer whose intention it is to modify and/or extend the software, several crucial things are important and also met by the software we are reviewing. At first, we need to remark that an extension of the software is enabled by the software being published on Github and is licensed under the GNU GPL license. This license not only enables other developers to reuse the software, but also the modification of the software for their own uses under the condition that the software is published under the same license.
As an open license which intends to promote the usage of free software, we think that this license is a good choice for a QGIS plugin. 
To get developers encouraged to work and extend a software, a clear and concise documentation of its purpose along with examples and a documented source code is very benefitial. In the case of the PointSampling Tool we can see that the software itself contains many comments in the given Python source code and it does not provide a HTML documentation which might give it a better accessibility especially for novice programmers. However, we must also acknowledge that the actual source code needed to execute the PointSampling Tool QGIS plugin is very limited and manageable, so one might argue that this is not hindering developers to get into extending the plugin.
As with any QGIS Python plugin being developed, the process to set up a plugin and to create QGIS plugins in general is well-documented by the QGIS application framework itself, so that the developer is in no immediate need to provide the documentation itself. It is in the nature of QGIS plugins that also not compilation process of the source code or other steps to build the application are needed, so that we can conclude that the building process is well-documented and easily comprehensible for the average developer.
However, what is not immediately obvious for a developer is the current state of implementation and application examples of the application. For this publication, we created example data to test the functionality of the QGIS Plugin - something a developer who wants to extend the plugin also needs to do in order to learn about all the plugin's features. Here, a developer would expect either some documented tests on how the functionality of the plugin could be assessed or example data which could be provided in the project repository which helps to sharpen the intention of the plugin as provided by the author.
Besides providing this insight for a developer, sample data can also be vital to explain the usefulness of a plugin for a new user or user group, so that we recommend the creation of a small tutorial page either on Github or another linked web resource.
Something we found very positive when reviewing the software was that feature requests and issues visible on Github have to the date of this review all been answered by the core developer and the developer has accepted pull requests of other programmers to extend the functionality of the plugin with ideas of the community. This shows a continued interest of the developer to care about the plugin. The fact, that the plugin did not receive frequent updates before the time of this review could be interpreted as a lack of interest of the developer, however it was our perception, that the main features of the plugin have now been implemented and that there is simply no need of a further active development at the present time.
Despite the perceived interest of the developer we would welcome a contribution guide, a small guide in which the developer states which extensions to the plugin are welcomed and in which form.

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


