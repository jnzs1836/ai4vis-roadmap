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



## Automatical Genration of Visualization

To-do


## Inverse Engineering on Viusalization and Visualization Recognition





## Text and Visualization
