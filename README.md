# ViveLesGC: How controversial and objective are today's news websites?


## Title
Interaction between controversy in newspapers and sales


## Abstract
The goal of this project is to assess how a news website popularity relate to its controversiality and objectivity, by analysing the quotations within its articles. 

Controversy, as defined in the [Merriam-Webster](https://www.merriam-webster.com/dictionary/controversy) dictionnary is a ***"discussion marked especially by the expression of opposing views"***. Therefore a topic that brings forth dispute and disagreement can be considered controversial, and by extension a newspaper prone to relating such kinds of subject can be said to be controversial. 

By developing a theory on how to quantify those parameters, a correlation between the number of users and the controversy level of each major news website would be determined. Therefore, those websites growth, during the time span of the dataset, would be explained along with the consumers preference towards biased or unbiased sources of information. 

Since it can be expected that users seek entertainment while searching for information the main question of the project would be: ***Can the search for profit make news websites more controversial?*** 

To answer this main question a controversy measure of each major news website will be done by analysing the controversy of the quotations within the medium. 


## Data story
Click the following link to access our amazing data story.


## Research Questions

- ***Detection of topics in a newspaper***
    > Using LDA (Latent dirichlet allocation) and coherence scores we are able to detect salient topics from our datasets. We set for 11 topics (each described by 11 distinctive words) as we obtained the highest coherence score for this number of topics. These topics will be analyzed to quantify the controversiality of the newspapers we will investigate. WE recall that topics are list of strings
    
- ***How to quantify controversiality of a topic in a newspaper?***
    >   In order to grasp how to quantify controversy you can look at [this paper](https://arxiv.org/abs/1512.05550) which details a method of assigning a controversy measure to hashtags on twitter by building retweet and follow graphs. In the same paper it was showcased that sentiment distribution in tweets could allow to differentiate controversial topics from non controversial topics. 
    We have used their findings as basis to motivate our controversy scores computation. Our controversy score is defined as : **2 * min(#positive_quotes, #negative_quotes)/#total_quotes** where "#" stands for "number of". This method is both simple and fast as no pairwise comparison is needed. It provides an "absolute measure of controversy".
    To validate our intuition behing this polarity-based score, we have compared our method to the variance-based method explained in the paper above.

- ***How to quantify controversiality for a whole newspaper?***
    > By summing over all relevant topics talked in the medium , a controversy score could be defined for the newspaper, it can be noted that some topic might hold more weight in terms of controversy, therefore an idea would be to use the ratio of occurence of the topic keyword as a weight for each topic. 

- ***How biased is a newspaper relative to other news outlets ?***
    > By using the tonality graph desribed above, an analysis of a newspaper subjectivity can also be carried out. In fact, for a given topic, a pattern in the graph can rise among different newspapers. The majority rule is then being followed for identifying subjective newspapers which in this case would represented as outliers since they won't follow the described trend.

- ***How controversial the most mentionned topics are?***  
    > By using the same data as for the previous question, it can be also analyse if the majority of news websites depicts a given topic as being controversial. Furthermore, the evolution of how a topic is depicted in the media could even be highlighted. For example, a study case on ***climate change*** can be made to show how major news outlets have described the issue over the years.

- ***Understanding controversy in newspapers and its correlation to sellings***
    > An interesting endeavour would be to investigate if any relationship exist between newspapers sellings and their controversiality. It is quite tricky to make as we do not know other covariates that could better explained this relationship. We will relate the two quantities and try to make sense of our observations.

## Proposed additional datasets

- Data concerning the popularity of the news website over the years,in particular **sellings**. We have considered 14 newspapers in the UK from 2015 to 2020.

## Get, manage, process, and enrich the datasets

Using the [Quotebank](https://quotebank.dlab.tools/) dataset the **N** quotations with most occurencies can be selected. Out of them, the quotes relayed by less than 3 newspapers are removed as they are less relevant for the study.

Since the data contain the quotation associated with the speaker and the link, the newspapers names can be obtained by shortening the urls. Therefore, the newspaper name, independent of the url link, can be assigned as an additional parameter of the quotation. 

Consequently the distribution of newspapers that relates at least one of those **N** quotations can be plotted to see which news websites relay the most "famous" quotations.

Additionally, by looking at only one quote (the most relayed one for example as it is done in the notebook), the distribution of the newspapers that relayed it can be highlighted. In fact, it is interesting to see that it follows a power law, with many journals that relay the same quote many times, while other relay it only once.

The quotations associated to a topic by searching for the topic keywords can be obtained. This is the first step towards the graph construction since it is possible to get all quotations that relates to a subject. A second step would be to get the sentiment score of the quotations. Currently a graph to relate speaker-newspaper has been drawn to visualize how the following steps would be carried out.


## Methods implemented
-   Filter dataset to get the news website of interest for the study.

-   Detect meaningful topic from newspapers
    We have used LDA (Latent dirichlet allocation) to detect topics
    
-   Quantify controversy using polarity scores (with NLP libraries)
    We designed our own method for computing 'absolute' controversy score.
    
-   Compare our method to existing methods from literature
    We validated our modeled against existing models by building search trees and running "top-k closest queries"

-   Compute global controversy score of newspapers 

## Main python libraries 
Pandas
Numpy
networkx
seaborn
matplotlib
ntlk
plotly
Scipy
VaderSentiment
sklearn


## Proposed timeline
- **12 Nov 2021**:
    > Milestone 2 delivered - End of documentational research on the project 

- **19 Nov 2021**:
    > Data story design determined 
    > Implementation of the NLP and graph construction methods  


- **26 Nov 2021**:
    > Updating/Correcting the methods 


- **3 - 17  Dec 2021**:
    > Analysis of the data - making relevant plots - adding figures and text to the website

## Organization within the team:

**Everyone will work on building the theory, the code, the website, but each person is in charge of a department, and anyone has to come to him if any question arises while working for his department.**

- Arthur: graphs visualisation
- Paul: sentiment analysis
- Fadel: theory implementation 
- Yannick: data story design 

