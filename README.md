# ADA_ViveLesGC

# How controversial and objective are today's news websites?

## Abstract
The goal of this project is to assess how a news website popularity relate to its controversiality and objectivity, by analysing the quotations within its articles. 

By developing a theory on how to quantify those parameters, a correlation between the number of users and the controversy level of each major news website would be determined. Therefore, those websites growth, during the time span of the dataset, would be explained along with the consumers preference towards biased or unbiased sources of information. 

Furthermore, the evolution of how a topic is depicted in the media could be highlighted. For example, a study case on ***climate change*** can be made to show how major news outlets have described the issue over the years.

Since it is expected that users seek entertainment while searching for information the main question of the project would be: ***how the search for profit make news websites more controversial?*** 
To answer this main question a controversy measure of each major news website will be done by analysing the controversy of the quotations within the medium. 

## Research Questions

- ***How to quantify controversy in a newspaper?***
    >  Controversy, is defined as a **discussion marked especially by the expression of opposing views** according to [Merriam-Webster](https://www.merriam-webster.com/dictionary/controversy). Therefore a statement that brings forth dispute and disagreement can be considered controversial. In order to grasp how to quantifying controversy you can look at [this paper](https://arxiv.org/abs/1512.05550) which details a method of assigning a controversy measure to hashtags on twitter by building retweet and follow graphs.	

    > In the case of this project, a given newspaper would be assimilated to a social media. Within the news outlet multiple topics are discussed and the goal would be to assess how controversial each topic is.  For a given subject, quotations relating to the subject key word can be found and by analysing its tone through NLP techniques for sentiment analysis (see 8.2 in the [paper](https://arxiv.org/abs/1512.05550)) a positive/negative sentiment score can be assigned to each quotations. Afterward, a graph with the following properties can be built:
            |	Vertex | quotation that relates to the topic |
	        	    | ----------- | ----------- |
            |	Edge | link between quotations with close polarities |
            
    > The main hypothesis is that the constructed graph will either have one or two clusters, with the second case occuring when the topic is highly controversial since the quotations aggregates into two sets with opposite sentiments. By quantifying the clusterization of the graph, a controversy measure could be assigned to the topic. By summing over all relevant topics talked in the medium , a controversy score could be defined for the newspaper, it can be noted that some topic might hold more weight in terms of controversy, therefore an idea would be to used the ratio of occurence of the topic keyword as a weight for each topic.
    
    A skematization of the proposed model is given below (see dessin_1.png):
   

<img src="/dessin_1.png" width=30% height=30%>


- ***How biased is a newspaper relative to other news outlets ?***
    > By using the tonality graph desribed above, an analysis of a newspaper subjectivity can also be carried out. In fact, for a given topic, a pattern in the graph can rise among different newspapers as such if this trend is not followed by some news website then they can be seen as being subjective for the topic. 

- ***How controversial the most mentionned topics are?***  
    > By using the same data as for the previous question, it can be also analyse if the majority of news websites depicts a given topic as being controversial. By looking at the controversy

- ***How to quantify how objective is a newspaper ?***
	> The following hypothesis is being made: To balance the statement made in a quote, there should be a ***counter-quote*** stating an opposite truth somewhere in the same article or newspaper in order to be objective.



### Proposed additional datasets

- Data concerning the popularity of the news website over the years, such as the number of daily users, suscribers, viewers etc... 

- Depending on the advances on the project, the datasets could be extended to years prior to 2015 in order to assess the websites growth over a greater time span. 

### Get, manage, process, and enrich the datasets.

We need to show that we've read the docs and we need some examples to show that we have a clear idea on what to expect__

### Methods to implement
-	Filter dataset to get the news website of interest 
-	Get a counter-quote from a given quote:
	- by searching for the negation of the given quote 
	- by analyzing the quote (meaning, polarity etc..), then creating a sentence with an opposite  meaning and searching   
-	Quantify controversy and objectivity: 
    - by implementing the mathematical equations derived from the theory descibed above (in Research Questions)

### Proposed timeline
> **12 Nov 2021**:
> Milestone 2 delivered - End of documentational research on the project - Aggregation of all the datasets 

> **19 Nov 2021**:
> Website design determined 
> Implementation of the **get_counter_quote** and **filter_dataset** methods 
> Mathematical model to quantify controversy and objectivity finished

> **26 Nov 2021**:
> Updating/Correcting the methods 
> Adding **quantify_controvresy** and **quantify_objectivity**
> Determining the graphs that are going to be plotted
> Building website framework

> **3 - 17  Dec 2021**:
> Analysis of the data - making relevant plots - adding figures and text to the website

### Organization within the team:
__TO BE DETERMINED__



