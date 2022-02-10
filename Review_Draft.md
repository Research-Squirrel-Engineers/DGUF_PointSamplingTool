---
title: Software Review for the Software PointSamplingTool

abstract_de: 
abstract_en: 
layout: draft
author:
  -
    name: Timo Homburg
    affiliation: Hochschule Mainz
    orcid: 0000-0002-9499-5840
    bio: "Timo Homburg studied computer science with a focus on computational linguistics (assyriology), semantic web and sinology. In recent years, he has worked in the field of GIS applications in geoinformatics. His doctoral thesis deals with better integration of geodata into a Semantic Web environment. His current research project deals with the design and establishment of digital standards in the field of assyriology and a best practice for documentation of excavations with cuneiform texts - an extension of his publications on 'Cuneiform Script in the Digital Humanities'."
  -
    name: Anne Klammt
    affiliation: Deutsches Forum für Kunstgeschichte Paris
    orcid: 0000-0003-3697-9241
    bio: "Archaeologist Anne Klammt completed her doctorate on a landscape archaeology topic and has been responsible for the further development of Digital Art History at the German Forum for Art History Paris as Head of Research since 2020."
  -
    name: Hubert Mara
    affiliation: mainzed & Hochschule Mainz
    orcid: 0000-0002-2004-4153
    bio: "Hubert Mara studied computer science at the Vienna University of Technology. There he already worked on digital methods in archaeology for ceramic analysis. He was subsequently a Marie Curie Fellow at the University of Florence within the framework of the *Cultural Heritage Informatics Research Oriented Network* (CHIRON). He completed his doctorate at the University of Heidelberg in the *Interdisciplinary Centre for Scientific Computing* (IWR). There he developed the [*GigaMesh Software Framework*](https://gigamesh.eu) and installed the *Forensic Computational Geometry Laboratory* (FCGL). Since June 2020, he has been the managing director of mainzed and is a researcher at the Institute for Spatial Information and Measurement Technology at Mainz University of Applied Sciences."
  -  
    name: Clemens Schmid
    affiliation: Max Planck Institute for the Science of Human History
    orcid: 0000-0003-3448-5715
    bio: "Clemens Schmid studied prehistoric, historical and scientific archaeology as well as computer science in Tübingen and Kiel. After graduating, he worked with computational data analysis in various archaeological research projects at the University of Kiel, the Roman-Germanic Central Museum in Mainz and the University of Bern. Now he is employed for a PhD project on quantitative estimation of past human mobility with ancient genetic and historical-linguistic data at the Department of Archaeogenetics of the Max Planck Institute for the Science of Human History in Jena."
  -
    name: Sophie Charlotte Schmidt
    affiliation: Freie Universität Berlin
    orcid: 0000-0003-4696-2101
    bio: "Sophie C. Schmidt studied Ancient Studies and Prehistoric Archaeology at the Free University of Berlin. She then worked as a research assistant in the field of archaeoinformatics at the universities of Cologne and Bonn, and at the NFDI4Objects consortium project at the German Archaeological Institute. Right now she works on her PhD project on 5th mill. BC in Brandenburg at the Free University Berlin."    
  -
    name: Florian Thiery
    affiliation: Römisch-Germanisches Zentralmuseum – Leibniz-Forschungsinstitut für Archäologie
    orcid: 0000-0002-3246-3531
    bio: "Florian Thiery studied geodesy and is a Research Software Engineer (RSE) in the *Scientific IT, Digital Platforms and Tools* department at the Römisch-Germanisches Zentralmuseum in Mainz. He is the initiator of the *Research Squirrel Engineers*, a network for RSEs in the Digital Humanities that pursues community projects with a focus on free and open data, as well as Linked Open Data. As part of a fellowship of the *Wikimedia Fellow-Programm Freies Wissen*, he is working on the modelling of Irish ᚑᚌᚆᚐᚋ (Ogham) stones and their publication in the Wikimedia universe."    
  -
    name: Martina Trognitz
    affiliation: Austrian Centre for Digital Humanities and Cultural Heritage, ÖAW Wien
    orcid: 0000-0003-0485-6861
    bio: "Martina Trognitz studied computational linguistics and classical archaeology in Heidelberg. From 2012 to 2017, she worked in the IANUS project at the German Archaeological Institute. Since 2017, she has been in charge of the digital archive ARCHE of the ACDH-CH at the Austrian Academy of Sciences. She is working on a PhD project on the machine analysis of multi-sided Aegean seals of the Bronze Age."


bibliography: bibliography.bib
csl: apa-6th-edition.csl
keywords:
  - Archäologie
  - Archäoinformatik
  - Softwarebewertung
  - Forschungssoftware
  - Rezension
  - QGIS
keywords_en:
  - archaeology
  - digital archaeology
  - software review
  - research software
  - review
  - QGIS

---


# Software Review for the Software PointSamplingTool

The QGIS Point sampling tool by Borys Jurgiel is a QGIS plugin, which samples polygon attributes and raster values from multiple layers at specified sampling points: https://plugins.qgis.org/plugins/pointsamplingtool/ .

The latest stable version is 0.5.3

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

In archaeology, the analysis of site factors of settlements and the correlation of sites and geographic conditions (land use, elevation, slope, accessibility, etc.) are questions that have been pursued with cartographic methods for more than 100 years [@grunwald_2016, 112]. These investigations can nowadays be carried out almost seamlessly with the help of Geographic Information Systems. In many cases, e.g. if a site size is unknown [@miera_2020, 103], queries for the distribution of certain factors, such as soil type or land use are often employed on the simplest geometric features - points.

Here, the Point Sampling Tool serves as a workhorse, as it is designed to facilitate the task of obtaining values of overlying geographic features such as soil types at points of interest: The geographic information are stored in maps, that can be digitized or - increasingly so - are generated born digital. Once the information is held geo-referenced and in a GIS compatible format and the location of sites is held in a digital format as well, the QGIS point sampling tool can be used to transfer the relevant information from the maps to the site location, by adding them as attributes to the geometry of the points in request. The output table can then be further analysed according to the archaeological question.

Two of the reviewers used the tool in their research and teaching (@Klammt_2015, @schmidt_2016). Both focus on gathering information regarding the geographical settings of archaeological sites and analysing them statistically in respect to site evidence and settlement activities. The usage of the point sampling tool formed a necessary but hardly remarkable part of their research routine, so both did not expand on the tool in their theses. As the tool is probably also rarely cited by other authors, we name here some studies for which it could have been used since its first release in 2008: @miera_2020, @hinz_2014, @cappenberg_2020.

Though useful for archaeological questions, the point sampling tool is a universal helper and not specifically shaped for archaeological use. Other disciplines employing it may be digital cartographers (see, e.g. Arco 2013: https://digital-geography.com/qgis-plugins-point-sampling-tool/), biologists or ecologists (http://wiki.awf.forst.uni-goettingen.de/wiki/index.php/Object-based_classification_(Tutorial)) or anyone using GIS software.

#### Workflow of the QGIS Point Sampling Tool

The Python-based Point Sampling Tool extracts information from layers ("maps") loaded to QGIS at points specified by a point layer and adds this information to the attribute table of the points. It is capable of sampling both multiple raster and vector layers within QGIS simultaneously. In doing so, it follows a routine that addresses the vector layers first and then the raster data (if both data types are included at the same time). This process sequence also determines the arrangement of the attribute fields. 

For multiband raster data the user has to decide which bands he wishes to sample (several bands at once are possible). For vector the attributes have to be selected - again it is possible to include all attributes. The number of resulting records is identical to the number of input points. For each vector layer only one geometry (feature) at one sampling point is taken into account, that is the last one in the processing, i.e. the one with the highest id. Therefore the point sampling tool can not be used for obtaining complete and fully controlled values form vector layers with several overlaying geometries. The latter could for example be the case for layers with overlapping buffers of sites or geographical feature that partly overlay each other.

The algorithms have been implemented correctly.

### Usability and target group orientation

The software is published as a QGIS python plugin: https://plugins.qgis.org/plugins/pointsamplingtool/ .

Since the Point sampling tool is a plugin, the software naturally requires the installation of the standalone QGIS software. Hardware requirements and possible limitations of QGIS itself are accordingly outside the scope of this review. 

#### Installation

The installation follows along the routine of the QGIS Plugin dialog. As the tool is not part of the geo processing toolbox, it does not align to it in the menu, but users will find it from the drop down menu of "plugins". From long lasting experience in introductionary courses on QGIS, the authors underline, that this is a considerable threshold for archaeologists, who are not working constantly with QGIS but only occasionally for carrying certain tasks. Still, this sometimes slightly confusing arrangement of the plugins in the menu is an overall usability backdrop of QGIS and not an issue that the point sampling tool is to blame for.

<!---* :heavy_exclamation_mark:**Are necessary requirements in terms of hardware and operating system clearly documented?** 

- No, but one might infer them from QGIS --->

#### Interface

The plugin comes in English only.

The Graphical User Interface follows the rather decent overall design and logic of the QGIS tool dialogues: It opens up with an assistant that gives the user full control to chose the layer that holds as points the locations as well as the layers to be sampled. Furthermore the user has to indicate which attribute-values from the source and the sample layer(s) should be part of the resulting new point layer. As it comes to raster data this means the selection of the raster band. A second tab gives a preview of the attribute table. The third, as it is the convention for QGIS Plugins, informs about the tool. Here the warning, that the tool does not align to multipoint-features, is placed relatively well. There is however no logfile, that facilitates the documentation and by that the reproducibility.

Here we feel that the usability offers certain thresholds. Firstly it would add to the usability, if one can include into the process also layers, which are not actively in display. Wherever granular vector data are involved QGIS considerably slows on computers which do not apply to special requirements of large data processing. Here often a workaround is to not display the data while processing them. From our experience researchers and students rely mostly on lesser powerful hardware. 

Secondly depending on the number of fields the input point layer carries as well as the overlayed layers the selection of the attribute-fields quickly becomes confusing, tiring and facilitates errors. And as for example geodata on soil types often brings a quantity of attribute fields, this may concern archaeologists. A possible solution could be a partition of the dialogues between source and overlayed layers as shown by the core plugin "intersection " for the geoprocessing of vector layers. 

Thirdly the tool does not allow identical field names for the resulting point layer, as this would indeed complicate or even prevent the user to interpret the resulting layer correctly. Luckily enough the tool offers a way to rename the fields before on the fly before starting the process. Still the renaming is restricted by the maximal length of 10 chars - longer entries get truncated. In the reviewers experience this complicates matters in so far, as in combination of the lack of a logfile the comprehensibility of the resulting files is  affected by this.

Finally the tool does not offer a temporary layer as result like (again) so many of the core plugins. Temporary layers would be an advantage when the sampling of points is a step within a workflow that aims for example to achieve the overall distribution of a position property measured on all measurement points. Here one just unnecessarily stores data, of an intermediate value.

#### Communication with the user

Testing shows, that there are error messages as well as warnings. Errors encompass wrong or missing choices concerning the layers to be matched or identical fieldnames. A warning is given when layers of different coordination reference systems are used. As it is only warning it is possible to override the message. This allows seamless working with data that might have false metadata. Short status messages support the user in solving errors and problems.

#### Performance and Robustness

The point-sampling-tools integrates seamlessly into the QGIS environment. In our test environment it ran stable and robust with datasets up to 16.900 points on buffer layers with significant geometric overlap. The process took less than a minute.


#### Help features, tutorials and community

There are no tutorials offered by QGIS or the developer themselves but the very short README on github. The sheer number of 348.629 downloads (stated 6. February 2022 at [https://plugins.qgis.org/plugins/](https://plugins.qgis.org/plugins/)) shows though, this tool is widely used. A short online search brings up a number of tutorials from users, teachers and university courses. An example may be the blog post by Scott Arco: [https://digital-geography.com/qgis-plugins-point-sampling-tool/](https://digital-geography.com/qgis-plugins-point-sampling-tool/) , the tutorial by Ujaval Ghandi: [http://www.qgistutorials.com/en/docs/sampling_raster_data.html](http://www.qgistutorials.com/en/docs/sampling_raster_data.html) or the YouTube tutorial by Yannick Kremer: [https://www.youtube.com/watch?v=bAyxLC3npCA](https://www.youtube.com/watch?v=bAyxLC3npCA).

This is especially helpful, as they come in a variety of languages like French ([https://www.youtube.com/watch?v=QdkOPXssapg](https://www.youtube.com/watch?v=QdkOPXssapg)), Spanish ([https://www.cursosgis.com/como-trabaja-el-complemento-point-sampling-tool-en-qgis/](https://www.cursosgis.com/como-trabaja-el-complemento-point-sampling-tool-en-qgis/)) and Polish ([https://www.youtube.com/watch?v=KicHepZNaKA](https://www.youtube.com/watch?v=KicHepZNaKA)), so its use in an international context with multilingual research teams is facilitated.

If one wishes to gain more information, there are several points of departure (QGIS Documentation, the QGIS plugin repository  that leads the user to the code repository of the plugin at github ([https://github.com/borysiasty/pointsamplingtool](https://github.com/borysiasty/pointsamplingtool). Additionally the [QGIS Plugin repository](https://plugins.qgis.org/plugins/) gives a thorough description of the tool and its main objectives as well as a list of the versions history ([Point sampling tool](https://plugins.qgis.org/plugins/pointsamplingtool/)).  

There do not exist any specific training data for this plugin, as there is no official tutorial. Nonetheless any GIS course data can be used, that incorporates point data alongside vector and/or raster data.



#### Data ingest, interoperability and programming interfaces

Every dataformat supported in QGIS can be read in. Still, matching the task it is supposed to perform, only point feature (no multipoints) can serve as input layers. The results of the process are outputed as Geopackage (dgpk) by default, csv and shapefile are as well offered.

The QGIS plugin does not offer a batch process. The input data and the parameters have to be manually chosen via the GUI. As stated in the context of the usability of the GUI this is a disadvantage.

The plugin support the QGIS processing API, which allows this plugin to be integrated into other QGIS (batch) proccessing tasks. 


### Developer perspective

From the perspective of a developer whose intention it is to modify and/or extend the software, several crucial things are important and also met by the software we are reviewing. At first, we need to remark that an extension of the software is enabled by the software being published on Github and is licensed under the GNU GPL license. This license not only enables other developers to reuse the software, but also the modification of the software for their own uses under the condition that the software is published under the same license.
As an open license which intends to promote the usage of free software, we think that this license is a good choice for a QGIS plugin. 

To get developers encouraged to work and extend a software, a clear and concise documentation of its purpose along with examples and a documented source code is very benefitial. In the case of the PointSampling Tool we can see that the software itself contains many comments in the given Python source code and it does not provide a HTML documentation which might give it a better accessibility especially for novice programmers. However, we must also acknowledge that the actual source code needed to execute the PointSampling Tool QGIS plugin is very limited and manageable, so one might argue that this is not hindering developers to get into extending the plugin.
As with any QGIS Python plugin being developed, the process to set up a plugin and to create QGIS plugins in general is well-documented by the QGIS application framework itself, so that the developer is in no immediate need to provide the documentation itself. It is in the nature of QGIS plugins that also not compilation process of the source code or other steps to build the application are needed, so that we can conclude that the building process is well-documented and easily comprehensible for the average developer.

However, what is not immediately obvious for a developer is the current state of implementation and application examples of the application. For this publication, we created example data to test the functionality of the QGIS Plugin - something a developer who wants to extend the plugin also needs to do in order to learn about all the plugin's features. Here, a developer would expect either some documented tests on how the functionality of the plugin could be assessed or example data which could be provided in the project repository which helps to sharpen the intention of the plugin as provided by the author.

Besides providing this insight for a developer, sample data can also be vital to explain the usefulness of a plugin for a new user or user group, so that we recommend the creation of a small tutorial page either on Github or another linked web resource.

Something we found very positive when reviewing the software was that feature requests and issues visible on Github have to the date of this review all been answered by the core developer and the developer has accepted pull requests of other programmers to extend the functionality of the plugin with ideas of the community. This shows a continued interest of the developer to care about the plugin. The fact, that the plugin did not receive frequent updates before the time of this review could be interpreted as a lack of interest of the developer, however it was our perception, that the main features of the plugin have now been implemented and that there is simply no need of a further active development at the present time.

Despite the perceived interest of the developer we would welcome a contribution guide, a small guide in which the developer states which extensions to the plugin are welcomed and in which form.

Finally, one could judge the quality of the implementation which has several aspects to consider. Because the software to be reviewed is a QGIS Plugin, certain constraints concerning its implementation are given by requirements on how a QGIS plugin is to be implemented. Therefore, these fundamental implementations details fall out of the judgement of this review. To get an idea about the quality of the actual implementation we refer to the test cases we have created for this publication in which we investigate the results of the plugin for various predefined datasets.

### Test case

We tested the software for firstly observe, how the point sampling tool copes with overlapping polygons, and secondly to check the performance on a rather large dataset. 
For this purpose we selected more or less randomly a rectangular area of 240 x 160 km in northern Germany and created two layers with point features and one with polygon features. The first point layer (A) comprises 360 features spaced 10.000 m apart  (fig. 1). These points were buffered with a radius of 22.000 m (polygon layer C) so that each point effectively overlaps several of the circular buffers. The second point layer (B) consists of 16.905 features spaced 1.500 m apart, with a slight offset from point layer A (fig. 2). The point samples of layers A and B were taken on polygon layer C.  The resulting point layers were stored as GeoPackages (GPKG). 
When sampling from layer A to C, we found that if the polygons overlap (six for the top left point and 13 for a point in the middle in the test case), the tool samples the polygon with the highest value as the ID (fig. 3). Using the sampling tool on Layer B shows that the process did not finish for 12 minutes due to the large amount of points. During the process, QGIS was not able to perform other tasks in parallel. It should be noted, however, that the sheer volume of points seems to us to be a rather unusual use case for archaeology.
The test was carried out with QGIS vers. 3.10, Coruna, on a Notebook (Intel Core i5-8265U bits) with Linux Mint 20.1. The test data and a visualisation are available at [https://github.com/Research-Squirrel-Engineers/pointsamplingtool-testdata](https://github.com/Research-Squirrel-Engineers/pointsamplingtool-testdata). 

---

### figure captions

![Testdata 1](images/testdata1_vers1.tiff)
*Fig. 1 Randomly chosen location of sampling points (layer A) in Northern Germany. Geodata: Map tiles by Stamen Design, under CC BY 3.0. Data by OpenStreetMap, under ODb. Image: authors*

Fig. 2 Sampling points layer A (blue dots) and layer B (yellow dots) with slight offset. Image: authors.

Fig. 3 Detail with only some of the polygons of layer C and their ID. The sample of the point in the upper left corner is taken of the polygon "ID 48". Image: authors.

---

| fig. | file |
| --- | --- |
| fig. 1 | images/testdata1_vers1.tiff |
| fig. 2 | images/testdata3_vers1.tiff |
| fig. 3 | images/testdata2_vers1.tiff |

