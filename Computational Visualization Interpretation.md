## Computational Visualization Interpretation

## Summary

| System                                                       | Inputs                                                       | Outputs                                                      | Method                                                       | data                                                         | publication    |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | :----------------------------------------------------------- | ------------------------------------------------------------ | -------------- |
| Reverse-Engineering Visualizations                           | chart bitmap image                                           | visual encoding speciﬁcation                                 | using inferred text elements                                 | a combination of automatically generated charts and manually annotated charts from 3rd party sources | EuroVIS 2017   |
| Extracting and Retargeting Color Mappings from Bitmap Images of Visualizations | chart bitmap image                                           | color encodings                                              | Color Legend Identiﬁcation->Color Legend Classiﬁcation by CNN -> Color Extraction by algorithms -> Legend Text Extraction -> Associating the text values with the color information | Visualization images from both academic papers and the web sites of scientiﬁc institutions | TVCG 2017      |
| Deconstructing and restyling D3 visualizations               | D3.js visualization                                          | data, marks and mappings between them                        | Algorithms                                                   | d3.js visualizations from web                                | UIST’14        |
| A system for understanding imaged infographics and its applications | Imaged infographics located in document pages                | graphical symbols                                            | OCR and other algorithms basically rule-based                | pdfs                                                         | DocEng 07      |
| ReVision                                                     | chart images                                                 | chart type,  graphical marks and data                        | infer the chart types by SVM and use the specific types to extract data and graphical marks | A new corpus containing 2,601 chart images labeled with 10 categories using a semi-automated tool for querying Google image search. | UIST’11        |
| Scalable algorithms for scholarly figure mining and semantics | pdf files                                                    | figure metadata; does a figure contain sub-figures; classification, text summarization(only contains trends description) | classifying the compound visualizations by the features proposed by Pelka. Classifying the figure types by SVM and Random Forest | 6.7 million PDF ﬁles in CiteSeerX repository                 | SBD’16         |
| ChartSense                                                   | bitmap images                                                | chart types and data                                         | a semi-automatic approach, classifying types by GoogLeNet    | Collecting 5659 images from google and labeling them manually | CHI 2017       |
| iVoLVER                                                      | bitmap images                                                | new visualizations, data, chart types                        | relying on manual annotation to extract data and encodings.  | No                                                           | CHI 2016       |
| Scatteract: Automated extraction of data from scatter plots  | scatter plot images                                          | data                                                         | detecting ticks;  OCR to extract value; find the closest value of a point | generated scatter plots                                      | ECML PKDD 2017 |
| Data Extraction from Charts via Single Deep Neural Network   | bar and pie charts(the authors mentioned that the model could extended to other types by augmenting data and revising the model) | data                                                         | a framework of a single deep neural network, which consists of object detection, text recognition and object matching modules. | Simulated charts based on Microsoft Excel and the Matplotlib library | arXiv.2019.06  |
| Multimodal Deep Learning using Images and Text for Information Graphic Classification | Images and text                                              | six categories of the data pattern and trends.               | joined embeddings of image and text                          | VizML and other online images. human labeling after collecting | ASSETS’18      |
| Extracting Visual Encodings from Map Chart Images with Color-encoded Scalar Values | bitmap images of map                                         | visual encodings and data                                    | OCR -> Value Inference -> Projection Inference               | map images from scientific documents,                        | SIBGRAPI 2018  |
|                                                              |                                                              |                                                              |                                                              |                                                              |                |



### Interpreting Graphical Elements in Visualizations

*Deconstructing and restyling D3 visualizations*

In this paper, Harper and Agrawala proposed a system for deconstructing D3.js visualizations that extracts data, marks and mappings between them.  The technique exploits the fact that one can access both SVG elements and data directly in the web browser. The technique is limited in SVG-based visualizations which is only a small part of visualizations. 



*A system for understanding imaged infographics and its applications.*

This paper describes technical details and practical applications of the system they built for recognizing and understanding imaged infographics located in document pages. This technique perform vectorization on images and convert them into a set of lines, arcs in the vector form before graphical symbols are constructed. Then, it applied domain knowledge to to identify graphical symbols representing data for each chart type. 



*ReVision: Automated Classification, Analysis and Redesign of Chart Images*

ReVision applies computer vision and machine learning techniques to identify the chart type. It then extracts the graphical marks and infers the underlying data. Using a corpus of images drawn from the web, ReVision achieves an image classiﬁcation accuracy of 96% across ten chart categories. They labeled the data manually.

### Interpreting Text in Visualizations

*Reverse-Engineering Visualizations: Recovering Visual Encodings from Chart Images*

This paper proposed a text analysis pipeline that identifies text elements in a chart image, determines their bounding boxes, recognizes the text content using OCR, and classifies their role in the chart (e.g., chart title, x-axis label, y-axis title, etc.). They also also train a Convolutional Neural Network that classifies the type of graphical mark used to encode data in a chart (e.g., bars, lines, points, or areas). Together, They leverage the inferred text and chart type information to recover a visual encoding specification in a declarative grammar similar to Vega-Lite [SMWH17] or Tableau’s VizQL [STH02]. This chart specification can then be used for indexing, search, or retargeting of the input visualization.



### Extracting Data From Visualizations

*Scalable algorithms for scholarly figure mining and semantics*

The paper reported scalable algorithms for generating semantic metadata for figures. The system has four sequential modules:

- Extraction of figure, caption and mention;
- Binary classification of figures as compound (contains sub-figures) or not;
- Three class classification of non compound figures as line graph, bar graph or others;
- Automatic processing of line graphs to generate a textual summary;

They inferred the textual summery simply based on the data trends.



*Curve Separation for Line Graphs in Scholarly Documents*

Line graphs are abundant in scholarly papers. They are usually generated from a data table and that data can not be accessed. One important step in an automated data extraction pipeline is the curve separation problem: segmenting the pixels into separate curves. Previous work in this domain has focused on raster graphics extracted from scholarly PDFs, whereas most scholarly plots are embedded as vector graphics. They reported a system to extract these plots as SVG images and show how that can improve both the accuracy (90%) and the scalability (5-8 seconds) of the curve separation problem.



*ChartSense: Interactive Data Extraction from Chart Images*

ChartSense uses a semi-automatic approach to extract data from line, pie and bar charts. The authors compared ChartSense with ReVision and found that ChartSense was more accurate than ReVision. 





*iVoLVER: Interactive visual language for visualization extraction and reconstruction*

Enabling flexible acquisition of many types of data (text, colors, shapes, quantities, dates) from multiple source types (bitmap charts, webpages, photographs, SVGs, CSV files), iVoLVER allows users to create visualizations without textual programming. In doing so,the authors used existing work that uses computer vision approaches to extract data from existing graphics.



 

*Data Extraction from Charts via Single Deep Neural Network*

The model performs successfully on 79.4% of test simulated bar charts and 88.0% of test simulated pie charts, while for charts outside of the training domain it **degrades** for 57.5% and 62.3%, respectively. 



*ReVision: Automated Classiﬁcation, Analysis and Redesign of Chart Images *

The authors presented ReVision, a system that automatically redesigns visualizations to improve graphical perception. Given a bitmap image of a chart as input, ReVision applies computer vision and machine learning techniques to identify the chart type. It then extracts the graphical marks and infers the underlying data.



## Restyling

*Extracting and Retargeting Color Mappings from Bitmap Images of Visualizations*

Visualizations “in the wild” often violate perceptual color design principles and may only be available as bitmap images. To address the problem, the authors contribute a method to semi-automatically extract color encodings from a bitmap visualization image. 



## Text and Visualization

*Multimodal Deep Learning using Images and Text for Information Graphic Classification*

If a graphic is not described, explained in the text, or missing alt tags and other metadata (as is often the case in popular media), the intended message is lost or not adequately conveyed. In this work, the authors describe a multimodal deep learning approach that supports the communication of the intended message.



## Others

*Beagle: Automated Extraction and Interpretation of Visualizations from the Web*  

The authors collected and extracted more than 41K SVG-based visualizations from the web. Rather than training a machine learning model or any thing, they use the data to study visualization usages. They found that most visualizations fall under four types: bar charts, line charts, scatter charts, and geographic maps. Though controversial, pie charts are relatively rare in practice. Our findings also indicate that users may prefer tools that emphasize a succinct set of visualization types, and provide diverse expert visualization examples.



*Evaluating ‘Graphical Perception’ with CNNs*

How do CNNs perform when applied to graphical perception tasks?

The authors investigated this question by reproducing Cleveland and McGill’s seminal 1984 experiments, which measured human perception efficiency of different visual encodings and defined elementary perceptual tasks for visualization. They measured the graphical perceptual capabilities of four network architectures on five different visualization tasks and compared to existing and new human performance baselines. While under limited circumstances CNNs are able to meet or outperform human task performance, they find that CNNs are not currently a good model for human graphical perception. 

 They also visualize the activation map of CNN and try to understand the recognition process of visualizations.



