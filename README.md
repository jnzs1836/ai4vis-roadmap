# AI4VIS-Roadmap-
A collection of papers on AI aided Data Visualization Generation and Analytic


```
Author: Guan-de Wu
Email: guadewu@gmail.com
```


## Datasets Summary
| Dataset  |Size| Data Structure| Text Description| Source Data |
|:------------:|:-------:|:----:|:---:|:--:|
|VizML|120K|plotly specifications| only titles|yes|
|VizML|31M|plotly specifications, other specifications and design choice| only titles|yes|
|Data2Vis|215K|vega-lite specifications|no|yes|
|Beagle|215K|vega-lite specifications|no|no|
|Viziometrics|4.8M|Figures|no but could collect|no|
|MassVIS|5K|Figures|no|no|
|theconversation.com|600|svg or pictures|yes|yes|
|theatlas.com|not sure but would not be too much| svg or pictures | no but could get collected | yes|


## Available Datasets

### VizML

*VIS4ML: An Ontology for Visual Analytics Assisted Machine Learning, CHI 2019*


The authors of VizML collect 120K visualizations together with the corresponding data from Plotly and put them available on github. However, there is no more text description other than the title in the dataset, which could be too short for us.


### VizNet

*VizNet: Towards A Large-Scale Visualization Learning and Benchmarking Repository, CHI 2019*


VizNet is a centralized and large-scale repository of data as used in practice, compiled from the web, open data repositories, and online visualization platforms. There are about 31M visualizations on it which is the biggest number of visualizations I have found. Howver, the dataset doesn't comprise much text descriptions either and we may need to collect the simple title text from the web by ourselves. Manyeye, which is one of the source websites of VizNet, has been closed now and we could not collect any title from it.



### Beagle

*Beagle: Automated Extraction and Interpretation of Visualizations from the Web, CHI 2018*


The authors extract over 41,000 SVG-based visualizations across ﬁve different tools and repositories including bl.ocks.org, Plotly, Chartblocks, Fusion Charts, and the Graphiq knowledge base. The resulting dataset comprises raw SVG speicifications and snapshots without any text description.


### Viziometrics
*Viziometrics: Analyzing Visual Information in the Scientiﬁc Literature, IEEE Transactions on Big Data, March 2018*

The authors developed a platform called VizioMetrics.org with which we analyzed 4.8 million ﬁgures from more than 650,000 PubMed Central papers. There are both normal figures and visualizations on the website but no dataset and text attached with. I think the text related to a figure could be extracted from the paper it belongs to while the missing data is difficult to find.



## MassVIS

*What Makes a Visualization Memorable?, InfoVIS 2013*

MASSVIS dataset is compiled from about 5K visualizations on the different websites. 
The dataset only comprise images even no data.

## Websites to Crawl


### Plotly

Like VizNet and VizML, the visualizations on Plotly only have the short titles which are too short for us. The advantage of Plotly is the visualizations on it comply with the Plotly json formats.




### the conversation

It is a news website on which there are a limit number of articles with visualizations. I have collected all visualizations and the total number is about 600.



### the Atlas

It is a new home for charts and data, powered by the news website Quartz. 
They provide both data and visualizations but also miss text description.
However, as the visualizations come from  the articels, We could find them by Google. I am not sure about the how much visualizations are on them but the answer would not be too big since a paper in 2017 mentiond that they use 475 visualizations on Quartz. 


(*Reverse-Engineering Visualizations: Recovering Visual Encodings from Chart Images*)





### Other News Websites

There are also other news websites containing visualizations, which could be categorized into two png files or svg-based visualizations.


Most of news websites use png or jpg files to deliver visualizations. I have collected some pictures files from those websites but only to find the most of figures are the normal pictures rather than visualizations. We could collect numerous figures from those websites but the classification of normal pictures and visualization pictures will be a time-consuming work. There is an example that the researchers employee ten students to do manual classifications on the visualization pictures in the paper *What Makes a Visualization Memorable*.



There are far less websites using svg-based visualizations like theconversation.com and quartz.com. Sometimes New York times would use svg-based visualizations but it is quite rare. 



## Automatic Generation of Visualization

To-do

## Inverse Engineering on Visualization and Computational Visualization Interpretation

There are two basic component types in a visualization image: text and graphical elements. In order to successfully deconstruct a visualization, one must be able to recognize both. However, most prior work focuses on graphical elements.

### Interpreting Graphical Elements in Visualizations

*Deconstructing and restyling D3 visualizations*

In this paper, Harper and Agrawala proposed a system for deconstructing D3.js visualizations that extracts data, marks and mappings between them.  The technique exploits the fact that one can access both SVG elements and data directly in the web browser. The technique is limited in SVG-based visualizations which is only a small part of visualizations. 



*A system for understanding imaged infographics and its applications.*

This paper describes technical details and practical applications of the system we built for recognizing and understanding imaged infographics located in document pages. This technique perform vectorization on images and convert them into a set of lines, arcs in the vector form before graphical symbols are constructed. Then, it applied domain knowledge to to identify graphical symbols representing data for each chart type. 



*ReVision: Automated Classification, Analysis and Redesign of Chart Images*

ReVision applies computer vision and machine learning techniques to identify the chart type. It then extracts the graphical marks and infers the underlying data. Using a corpus of images drawn from the web, ReVision achieves an image classiﬁcation accuracy of 96% across ten chart categories. They labeled the data manually.

### Interpreting Text in Visualizations

*Reverse-Engineering Visualizations: Recovering Visual Encodings from Chart Images*

This paper proposed a text analysis pipeline that identifies text elements in a chart image, determines their bounding boxes, recognizes the text content using OCR, and classifies their role in the chart (e.g., chart title, x-axis label, y-axis title, etc.). They also also train a Convolutional Neural Network that classifies the type of graphical mark used to encode data in a chart (e.g., bars, lines, points, or areas). Together, we leverage the inferred text and chart type information to recover a visual encoding specification in a declarative grammar similar to Vega-Lite [SMWH17] or Tableau’s VizQL [STH02]. This chart specification can then be used for indexing, search, or retargeting of the input visualization.



### Extracting Data From Visualizations

*Scalable algorithms for scholarly figure mining and semantics*

The paper reported scalable algorithms for generating semantic metadata for figures. The system has four sequential modules:

+ Extraction of figure, caption and mention;
+ Binary classification of figures as compound (contains sub-figures) or not;
+ Three class classification of non compound figures as line graph, bar graph or others;
+ Automatic processing of line graphs to generate a textual summary;

They inferred the textual summery simply based on the data trends.



*Curve Separation for Line Graphs in Scholarly Documents*

Line graphs are abundant in scholarly papers. They are usually generated from a data table and that data can not be accessed. One important step in an automated data extraction pipeline is the curve separation problem: segmenting the pixels into separate curves. Previous work in this domain has focused on raster graphics extracted from scholarly PDFs, whereas most scholarly plots are embedded as vector graphics. We report a system to extract these plots as SVG images and show how that can improve both the accuracy (90%) and the scalability (5-8 seconds) of the curve separation problem.



*ChartSense: Interactive Data Extraction from Chart Images*

ChartSense uses a semi-automatic approach to extract data from line, pie and bar charts.



*iVoLVER: Interactive visual language for visualization extraction and reconstruction*

iVoLVER relies on manual annotation to extract data and encodings.

## Text and Visualization
