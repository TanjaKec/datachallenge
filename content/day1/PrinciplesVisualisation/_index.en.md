---
date: "2016-04-09T16:50:16+02:00"
title: Introduction to Visualization Principles
menuTitle: "Principles of Visualisation"
weight: 9
---

## Designed to enable: exploration, discovery, communication

Graphical methods are commonly used for exploratory data analysis. Boxplots, scatterplot matrices, nonparametric smoothers and tree diagrams are just some of the mostly used graphical tools for data exploration. This part of the course will provide practical recommendation for choosing the best chart or graph type for creating good and clear graphics that would serve the purpose of communicating the key information 

1. to intended audience and the publication
2. to help readers answer the questions your graphic is showing
3. to understand it easy without getting bewildered   

### Graphical Forms::Encoding

Good and clear graphics rely most of all on a reliable data. Thus, the first principle of an effective visualisation is that it represents reliable information. The type of the information that needs to be communicated and displayed will direct the choice of the most appropriate type of data encoding that would make relevant patterns become noticeable. It is therefore important to understand the problem you wish to communicate and the type of the data you need for its communication from the statistical perspective, ie. is it measured, categorical (ordinal or nominal), time (temporal dimension) and geographical location (spatial dimensions) in case of spatiotemporal data. 

Visual encoding of a data set depends on the number and characteristics of the available attributes ie. variables and on the analytical problem in question. [Alberto Cairo](http://albertocairo.com) on his blog [The Functional Art](http://www.thefunctionalart.com/2013/08/in-infographics-steal-what-you-need-but.html) provides an effective list of the graphic forms used to encode data depending on the function of the display. The figure shows ranking of the elementary perception task according on how well they can be perceived based on the ground breaking work of Cleveland and McGill published in [the paper](http://euclid.psych.yorku.ca/www/psy6135/papers/ClevelandMcGill1984.pdf) of [JASA](https://amstat.tandfonline.com/toc/uasa20/current) while working in the famous AT&T Bell Labs. 
![Red variant](/day1/PrinciplesVisualisation/images/FunctionalForms.png?width=30pc)

The above figure illustrates the order in which graphical forms could be placed based on the accuracy of the conclusions which readers can draw about the given data from them. If, for example, the goal of the graphic is to facilitate precise comparisons, [Alberto](http://albertocairo.com) in his book [The Functional Art](http://ptgmedia.pearsoncmg.com/images/9780321834737/samplepages/0321834739.pdf) provides an effective illustration of superiorities between possible choices of the graphical forms that could be used.

![Red variant](/day1/PrinciplesVisualisation/images/choices_graphical_forms.png?width=20pc)

There is not a specific methodology that is develop for choosing the most appropriate ways of encoding data. You never know if a visual form will work until you give it a try. It mostly depends on what your attributes are that you using in order to revel that special something from the data. However, there are some useful guidelines made by a few authors of which I would recommend to check:

- [The Data Visualisation Catalogue](https://datavizcatalogue.com) by [Severino Ribecca](http://www.severinoribecca.one)
- [Chart Chooser](https://depictdatastudio.com/charts/) by [Depict Data Studio](https://depictdatastudio.com) and 
- [Visual Vocabulary](https://journalismcourses.org/courses/DE0618/Visual-vocabulary.pdf) by [by the Financial Times Visual Journalism Team](https://github.com/ft-interactive/chart-doctor/tree/master/visual-vocabulary) 

as a starting bench mark when creating a graph.  

Often, the graphical display of the information created for answering a specific question will invite further exploration, which is why it is important to present them in a clear and truthful manner. We should not forget that the sole purpose of data analysis, thus visualisation is to inform and to improve the knowledge. So yes, we should consider very carefully aesthetic appeal and design of the graph we create that could effectively engage with the audience, but should do so by focusing above all on accuracy, depth and clarity of its conveying information.     

#### Identify encoding

Let us play the game ‘Identify encoding!’. Converse with each other and make a list of graphical forms and the type of encodings used in each of the following visualisation:

1) Visualisation: [DESI](https://ec.europa.eu/digital-single-market/en/desi)

![Red variant](/day1/PrinciplesVisualisation/images/DESI.png?width=40pc)

2) Visualisation: [DESI Report 2019 - Human Capital](https://ec.europa.eu/digital-single-market/en/human-capital) 

![Red variant](/day1/PrinciplesVisualisation/images/DESI_Internet1.png?width=50pc)

3) Visualisation: [DESI Report 2019 - Human Capital](https://ec.europa.eu/digital-single-market/en/human-capital) 

![Red variant](/day1/PrinciplesVisualisation/images/DESI_ICT.png?width=40pc)

4) Click on Visualisation: [Gapminder Bubble Chart](https://www.gapminder.org/tools/#$chart-type=bubbles)

[![Red variant](/day1/PrinciplesVisualisation/images/Bubble_Chart.png?width=40pc)](https://www.gapminder.org/tools/#$chart-type=bubbles)

5) Click on Visualisation: [Gapminder World Population](https://www.gapminder.org/tools/#$chart-type=map)

[![Red variant](/day1/PrinciplesVisualisation/images/World_Pop.png?width=40pc)](https://www.gapminder.org/tools/#$chart-type=map)

6) Click on Visualisation: [Periodic Table](https://www.rsc.org/periodic-table)

[![Red variant](/day1/PrinciplesVisualisation/images/PeriodicTable.png?width=30pc)](https://www.rsc.org/periodic-table)

Click on this Visualisation too: [A Periodic Table of visualisation methods](http://www.visual-literacy.org/periodic_table/periodic_table.html)

7) Click on Visualisation: [Clinton Email Network](https://rud.is/projects/clinton_emails_01.html)

[![Red variant](/day1/PrinciplesVisualisation/images/ClintonEmails.png?width=30pc)](https://rud.is/projects/clinton_emails_01.html)

### The Complexity: effective visual design

The most important to remember when creating a graphical is to present data clearly and truthfully. The choice of the scale on the chart should show the differences in the data and communicates the range of values accurately. Any statistical summary displayed on the chart should be presented clearly with the source of information and statistics used to calculate the more complex figures. 

Here are some most obvious issues you need to pay attention to when designing an effective graph:

1)	**Choose a scale for your charts** that strikes a balance between demonstrating trends clearly and conveying the scale of the original dataset. The chart does not need to begin at 0 in order to establish a meaningful baseline if another logical starting point exists. 
[Dual-Scaled Axes in Graphs](https://www.perceptualedge.com/articles/visual_business_intelligence/dual-scaled_axes.pdf)

![Red variant](/day1/PrinciplesVisualisation/images/scale1.png?width=40pc)
![Red variant](/day1/PrinciplesVisualisation/images/scale2.png?width=40pc)

The choice of scale should allow for better accuracy that reader can draw about the information displayed on the chart.

Have a look at [What to consider when creating a line chart]( https://blog.datawrapper.de/line-charts/
) blog post by [Lisa Charlotte Rost]( https://blog.datawrapper.de/), where you will also find links to some more interesting posts on this topic.  

2)	Highlight the important data

3)	Declutter the chart – keep it simple






Choosing a Deficient Measure

Taming the information from the visual display should not be difficult. 

ability to make sense of and communicate it
[Dual-Scaled Axes in Graphs](https://www.perceptualedge.com/articles/visual_business_intelligence/dual-scaled_axes.pdf)


[![Red variant](/day1/PrinciplesVisualisation/images/USA2016ElectionMap.jpg?width=30pc)](http://cartonerd.blogspot.com/2018/03/dotty-election-map.html)



{{% notice note %}}
When creating a data visualisation, think about the specific information that you want your data to convey, or the outcome that you want to achieve. Keep it simple and remove any unnecessary elements that could convolute your central point, bombarding an audience with too much data will likely leave them doubtful and confused. 
{{% /notice %}}

"Graphical perception is the visual decoding of the quantitative and qualitative information encoded on graphs."
[Cleveland W.S. and McGill R. *Graphical Perception and Graphical Methods for Analyzing Scientific Data*. American Association for the Advancement of Science, 1985. **229(4716)**: 828-833](https://pdfs.semanticscholar.org/565d/843c2c0e60915709268ac4224894469d82d5.pdf)

{{% notice note %}}
ghjghjk
{{% /notice %}}

-----------------------------
© 2019 Tatjana Kecojevic
