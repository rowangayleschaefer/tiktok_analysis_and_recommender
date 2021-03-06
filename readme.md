<div id="top"></div>


<!-- PROJECT LOGO -->
<br />
<!--<div align="center">
  <a href="https://github.com/rowangayleschaefer">
    <img src="https://yt3.ggpht.com/ytc/AKedOLRcwXL5heetbKNzpLCY3LOgml-72EcmpALhcvry5g=s900-c-k-c0x00ffffff-no-rj" alt="Logo" width="80" height="80">
  </a>-->
<div align = "center">
<a href= "https://www.icloud.com/keynote/00cOYoPPZOmZjw5gyymV5e9Aw#tiktok_trends"><img src='https://github.com/rowangayleschaefer/tiktok_analysis_and_recommender/blob/main/images/tiktok_white.jpeg?raw=true' width=100 height=100 border=2>
</a>
  <h2>TikTok Trend Analysis and Video Recommender</h2>
  <h4>Completed for General Assembly, 2022</h4>
</div>
<p><br />
<!-- ABOUT THE PROJECT -->

<!-- BACKGROUND -->
#### This app is being created to help TikTok creators monitor the top and rising songs and hashtags by country/location. This is important due to the way that TikTok algorithm selects For You Page (FYP)  content for its users in 2022.


If you're a new TikTok creator, your content will only be recommended on the For You Pages (FYP) of users in your OWN country, until you gain a minimum number of followers to be suggested internationally.

Many people have tried to find a way around this. Changing your location on Tiktok is a complicated process that involves gps spoofing, a VPN, and having sim cards for all your target countries. 

Another option is that until creators have a large enough following, they need to prioritize creating locally targeted content. 
<br /><br />

<p align="right">(<a href="#top">back to top</a>)</p>
<br />


<!-- PROBLEM STATEMENT -->
## Problem Statement
Due to the location barriers that new tiktok creators face, a solution is needed to better analyze trends in non-US countries. Currently there are no web apps that allow you to cross compare trending content in different countries. 
<br /><br />


#### My intention is to design an app that could answer the following questions for a creator/business owner:

1. What are the top trending sounds in <code>country 1</code>?

2. What is the intersection of top trending sounds/hashtags in <code>country 1</code>, <code>country 2</code>, and <code>country 3</code>? 

3. Lastly, I built a recommender app to explore how content might be suggested, with the removal of the location barriers. 

<br />

#### Risks & assumptions:
* TikTok changes their algorithms often - so usefulness/relevancy of this information may decrease over time

* I had limited information available about the data fields that were pulled during data collection. Some inferences were made based on context and prior knowledge.

* Third party TikTok APIs break frequently and there is a good chance that the one I have used will break; code will need an overhaul eventually.

* Trends change constantly. Preprocessing steps will need to be continually re-evaluated in order for resulting analysis to hold any weight. See discussion on context for trending hashtags in the data cleaning file.


<p align="right"> (<a href="#top">back to top</a>) </p>
<br />


<!-- DATA -->
## Data Collection

I ended up using TikTok-All-In-One from FastAPI to collect data.  Data collection process was cut short early due to time constraints; overall 74,197 rows of data were pulled for 119 countries (A-K, with some extras.) 

Note that in the data there are a lot of extra fields that are not used. I chose to keep them around, so I could cross check and make inference about other fields. This was necessary due to not having documentation for the API.

In the future, collection for the remaining countries will need to be done with a virtual machine. 

Note that csvs in the data folder are redundant. When I update I intend to rework the collection, cleaning, and preprocessing steps for higher efficiency.

<p align="right">(<a href="#top">back to top</a>)</p>
<br />


## Data Cleaning
Data cleaning and preprocessing steps included filling nulls, countvectorizing hashtags, dropping a few columns that weren't useful, and some feature engineering (a column for FYP_location). 

See the data cleaning and modeling files for discussion on context for trending hashtags and how inclusion or exclusion of certain hashtags was determined for this project. (#fyp, #trending, #xyzbca, etc. It's complicated.)
In general, I decided to exclude hashtags from analysis that did not provide any new information or context. 

Note that a lot of columns were intentionally pulled from that data even though they weren't used; this is due to lack of documentation and needing to cross-reference other fields for context.

Data cleaning and data collection sections are being reworked; code could be simplified across entire project by optimizing data collection process. 

<p align="right">(<a href="#top">back to top</a>)</p>
<br />

## Preprocessing
Preprocessing steps differed for analysis and modeling sections of the project. Unique preprocessing steps for modeling included building out a dictionary of Gen-Z/social media-specific stopwords to reduce "noise" in the data, and preserving hashtags and @ symbol in word lemmatization.

The modeling portion of this project is intended as exploratory. I built a recommender model using only the description text from each video. 

For a detailed analysis of choices made for preprocessing, see the modeling.ipynb file. One thing to note is that I had to build out a fairly large dictionary of stopwords in order to keep the recommendations relevant. At this time I was not able to find a stopwords dictionary that takes gen z speech patterns and vocabulary into account.

<p align="right">(<a href="#top">back to top</a>)</p>
<br />

<!-- Modeling -->
## Modeling 

For this section I only used countries that spoke English or a derivative of English due to existing challenges of working with multilingual data AND working with trending content from a younger age group. (ie... checking if Russian gen Z slang is being lemmatized correctly.)

I did include Jamaica in my modeling since I'm somewhat familiar with Jamaican Patois. The model picked up on this quickly, and if given a video that included any patois in the description, it would return more Jamacian videos with high accuracy. 

The decision to keep the patois in the countvectorizer was intentional (but that decision could *easily* be challenged -- recommended videos were "relevant" in that descriptions used similar vocabulary and speech patterns, but topics of the videos were not always similar.)


One thing to note: even if recommending posts based on NLP and description text alone worked well, it could actually lead to more unintended consequences than simply setting hard location boundaries on creators. This is a separate  ethics conversation.



Final model recommends videos based on lemmatized video description text and hashtags included in description.

#### Risks & assumptions:
* The modeling portion of this project is intended as exploratory.
* Even if recommending posts based on NLP alone worked well, it could actually lead to more unintended consequences than setting hard location boundaries on creators. This is a separate ethics conversation.


<p align="right">(<a href="#top">back to top</a>)</p>
<br />

## Presentation
<div align="center">
<a href= "https://www.icloud.com/keynote/00cOYoPPZOmZjw5gyymV5e9Aw#tiktok_trends"><img src='./images/keynote.png' width=550 height=320 border=2><br />
  <center><sup>click for keynote</sup></center>
</a>
</div>


<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE.txt` for more information.

<p align="right">(<a href="#top">back to top</a>)</p>
<br />




