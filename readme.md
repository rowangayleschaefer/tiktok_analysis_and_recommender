<div id="top"></div>


<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/rowangayleschaefer">
    <img src="https://yt3.ggpht.com/ytc/AKedOLRcwXL5heetbKNzpLCY3LOgml-72EcmpALhcvry5g=s900-c-k-c0x00ffffff-no-rj" alt="Logo" width="80" height="80">
  </a>

<h2 align="center"> TikTok Analysis & Recommender</h2>
<h4 align="center">Completed for General Assembly, 2022</h4>
</div>
<br />

<!-- ABOUT THE PROJECT -->


<!-- BACKGROUND -->
## Background
---

If you're a new TikTok creator, your content will only be recommended on the For You Pages (FYP) of users in your OWN country, until you gain a minimum number of followers to be suggested internationally.

Many people have tried to find a way around this. Changing your location on Tiktok is a complicated process that involves gps spoofing, a VPN, and having sim cards for all your target countries. 

Another option is that until creators have a large enough following, they need to prioritize creating locally targeted content. 
<br /><br />


<!-- PROBLEM STATEMENT -->
## Problem Statement
Due to the location barriers that new tiktok creators face, a solution is needed to better analyze trends in non-US countries. Currently there are no web apps that allow you to cross compare trending content in different countries. 
<br /><br />


#### My intention is to design an app that could answer the following questions for a creator/business owner:

1. What are the top trending sounds in <code>country 1</code>?
2. What is the intersection of top trending sounds/hashtags in <code>country 1</code>, <code>country 2</code>, and <code>country 3</code>? 
3. Lastly, I built a recommender app to explore how content might be suggested, with the removal of the location barriers. 


#### Risks & assumptions:
* TikTok changes their algorithms often - so usefulness/relevancy of this information may decrease over time
* I had limited information available about the data fields that were pulled during data collection. Some inferences were made based on context.


<p align="right"> (<a href="#top">back to top</a>) </p>
<br />


<!-- DATA -->
## Data Collection

I ended up using TikTok-All-In-One from FastAPI to collect data.  Data collection process was cut short early due to time constraints; overall 74,197 rows of data were pulled for 119 countries (A-K, with some extras.) 

Note that in the data there are a lot of extra fields that are not used. I chose to keep them around, so I could cross check and make inference about other fields. This was necessary due to not having documentation for the API.

In the future, collection for the remaining countries will need to be done with a virtual machine. 


## Data Cleaning
Data cleaning and preprocessing steps included filling nulls, countvectorizing hashtags, and some feature enginerring (a column for FYP_location). 

Data cleaning and data collection sections need rethinking; code could be simplified across entire project by optimizing data collection. 

<p align="right">(<a href="#top">back to top</a>)</p>
<br />


<!-- Modeling -->
## Modeling

#### Risks & assumptions:
* The modeling portion of this project is intended as exploratory.
* Even if recommending posts based on NLP alone worked well, it could actually lead to more unintended consequences than setting hard location boundaries on creators. This is a separate ethics conversation.


<p align="right">(<a href="#top">back to top</a>)</p>
<br />



<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE.txt` for more information.

<p align="right">(<a href="#top">back to top</a>)</p>
<br />




