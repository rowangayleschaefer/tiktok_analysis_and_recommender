<div id="top"></div>


<div align="center">
<!-- PROJECT SHIELDS -->

[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![MIT License][license-shield]][license-url]
[![LinkedIn2][linkedin-shield]][linkedin-url]</div>

<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/rowangayleschaefer">
    <img src="https://yt3.ggpht.com/ytc/AKedOLRcwXL5heetbKNzpLCY3LOgml-72EcmpALhcvry5g=s900-c-k-c0x00ffffff-no-rj" alt="Logo" width="80" height="80">
  </a>

<h2 align="center"> tiktok creators tool</h2>
<h4 align="center">Completed for General Assembly, 2022</h4>
<h4 alight="center"> <a href="https://github.com/users/rowangayleschaefer/projects/4/views/2"> PROJECT KANBAN BOARD</a> </h4>
</div>
<br />



<!-- TABLE OF CONTENTS -->
<details> 
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#about-the-project">About The Project</a></li>
    <li><a href="#software-requirements">Software Reqs</a></li>
    <li><a href="#data">Data</a></li>
    <li><a href="#data-cleaning">Data Cleaning</a></li>
    <li><a href="#eda">Exploratory Data Analysis</a></li>
    <li><a href="#findings">Findings</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>
<p></p>


```diff
- BRAINSTORMING / TO DO:

- 1. Data is collected enough.

@ PREPROC
- 2. <1 HOUR: word encoding, pull out hashtags
+ spacy vs sklearn sugg?



@ BY SATURDAY NIGHT
- 2. Exploratory viz - DONE ON SATURDAY 10PM - automated with sweetviz. https://pythonhosted.org/speedml/speedml/   https://github.com/mstaniak/autoEDA-resources
+ better libraries? faster

- 3. Main analysis - data only - 2 HOURS. SHOULD NOT TAKE LONG

- 4. Main analysis - interactive viz - 10 hours unless there's a faster way. low level plotly is annoying?
+ fastest way that isn't tableau?


@ BY SUNDAY NIGHT
- 4. Non-functional streamlit app/shell - 2 HOURS. HEX VS STREAMLIT VS PYSCRIPT figure out which will be fastest.

- 5. FUNCTIONAL but ugly app - 





- ONLY IF TIME

- Script to postgre database (check w/ danny - may be faster.)


```

<!-- ABOUT THE PROJECT -->

## About

#### This app was created to help TikTok creators monitor the top and rising songs and hashtags by country/location. This is important due to the way that TikTok algorithm selects For You Page (FYP)  content for its users in 2022.

<br />

<!-- BACKGROUND -->
## Background
<img src='./images/divskinny.png'>


#### Why does location matter?
If TikTok a creator has fewer than [???](https:///www.google.com) followers, their videos are only recommended on the For You Pages of users in their OWN country. 
This means that until creators have a large enough following, they need to prioritize creating locally targeted content until they reach the minimum following threshold to be suggested internationally.
<br /><br />


#### Why is this a problem?
**This limitation makes it difficult for new creators to significantly expand their reach or increase their number of followers, especially if they are making niche content and most of their target audience lives outside of their home country.  For example:** <br />
* The majority of users within your business niche or industry live in a different country than you. You are making industry relevant content but it is not recommended to your target  audience due to the location restrictions. You struggle to gain enough followers to be suggested internationally.
* You are using TikTok for your business, so you only follow industry related accounts - most of which are located in a different country than you. As a result, you see content from your country less frequently and lose exposure to local trends. You begin making content with trending sounds and hashtags from the wrong locality, and struggle to get views.
<br /><br />


#### Changing your location</u>
**TikTok determines location of a user or creator based on THREE pieces of information:**

1. Their GPS location
2. their IP address
3. their SIM card

If you use a VPN and change the GPS location on your phone, this may change what your location is *displayed as* in your user settings and profile. **However, fully modifying your location internally requires [Having multiple SIM cards for diff countries, hardware requirements,  etc etc link.](https://www.google.com)** In short, they have made it as difficult as possible, but it is possible.

<p align="right"> (<a href="#top">back to top</a>) </p>
<br />


<!-- PROBLEM STATEMENT -->
## Problem Statement
<img src='./images/divskinny.png'><br />

**For creators who don't have the time, money, or desire to manage multiple devices and SIM cards, a solution is needed. As of Feb 2022 there was not an app that allowed users to see  worldwide trends on TikTok (However there were apps for select countries, such as the USA and Malaysia.) For other countries, the only way to get this information is to make multiple TikTok accounts for each country/industry pair, follow relevant accounts/hashtags, train the algorithm to show you more of what you want to see, and draw your own conclusions by scrolling regularly. This is time consuming.** 
<br /><br />


#### My intention is to design an app that could answer the following questions for a creator/business owner:

1. What are the top trending sounds in <code>country 1</code>?
2. What is the intersection of top trending sounds/hashtags in <code>country 1</code>, <code>country 2</code>, and <code>country 3</code>? 
3. What are the top trending sounds for users living in  <code>country 1</code>  who follow <code>hashtag 1</code>?
4. What are the top trending sounds and hashtags for all users in <code>country 1</code> who follow <code>influencer account 1</code>?
<br /><br />


#### Use cases:

* You're following a lot of international accounts and want to double check that the trends you're using are relevant for your reach level.
* You want to isolate tiktok trends in both your industry/niche AND your country, to fine tune content for the *accessible* part of your target audience.
* You want to cross reference TikTok trends from multiple countries at once in order to increase views in all of them.
* You need a very quick source of info on TikTok trends in a different country.

*This project was created with #DataTok and Australia in mind, so prototype app will prioritize delivering stats for these two categories.*
<br /><br />


#### *Bonus Research Questions*

The location based limits were put in place in order to ensure that users would see content that was relevant and understandable to them. There are many cases where it's detrimental, and keeps users from seeing content that's a good fit for their interests and culture. For example - content being uploaded by Toronto-based creators is probably relevant, relatable, and understandable to users living in northern Michigan.

If there's time, I'll explore alternative ways of clustering users without using their country as a defining characteristic.
<br /><br />


#### Risks & assumptions:

* Since primary use of this app will be for analysis, there are not as many risks or assumptions made.
* However, TikTok changes their algorithms often - so usefulness/relevancy of this information may decrease over time.
* Risks and assumptions will be discussed separately for modeling section.

<p align="right"> (<a href="#top">back to top</a>) </p>
<br />


<!-- DATA -->
## Data
<img src='./images/divskinny.png'><br />

```diff
- TO DO

- 1. Data collection done enough.
- 2. IF TIME, LATER: Script to postgre database

```

Data was scraped from tiktok using .<br />

Vivamus pretium et sapien quis condimentum. Duis facilisis dolor in nisl sagittis, et condimentum magna finibus. Donec ornare imperdiet arcu eget egestas. Nunc gravida arcu non risus imperdiet, eget faucibus ante elementum. Interdum et malesuada fames ac ante ipsum primis in faucibus. Aenean id eleifend turpis. Donec lacinia neque rhoncus, luctus enim eget, tempor elit. Nam sit amet imperdiet neque, ullamcorper ornare tortor. Cras eget metus ex. <br />


<p align="right">(<a href="#top">back to top</a>)</p>
<br />

 
 
<!-- WEB APP -->
## Web App
<img src='./images/divskinny.png'><br />

<img src='https://powerslides.com/wp-content/uploads/2021/01/Data-Analysis-Template-02.jpg' alt='Placeholder Image' >><br />

```diff
- TO DO
- 1. BY 5/27: Clarity on backend process

- 2. BY 5/27: Figure out optimal/least painful interactive viz library to let users filter data in multiple ways

- 3. BY 5/30: Commit to either pyscript or streamlit

- 4. BY 5/30: Make bad prototype, put it on web

```

<br /> 

App built with streamlit or pyscript, whichever is easier. If histing the app isn't working, replace with highlights section. Vivamus pretium et sapien quis condimentum. Duis facilisis dolor in nisl sagittis, et condimentum magna finibus. Donec ornare imperdiet arcu eget egestas. Nunc gravida arcu non risus imperdiet, eget faucibus ante elementum. Interdum et malesuada fames ac ante ipsum primis in faucibus. Aenean id eleifend turpis. Donec lacinia neque rhoncus, luctus enim eget, tempor elit. Nam sit amet imperdiet neque, ullamcorper ornare tortor. Cras eget metus ex. <br />

<p align="right">(<a href="#top">back to top</a>)</p>
<br />





<!-- Modeling -->
## Modeling
<img src='./images/divskinny.png'><br />


```diff
- TO DO

- 1. BY 6/3: Decide if there's time/enough data.

- 2. BY DATE: Bullet

- 3. BY DATE: Bullet

```

Clustering if there is time. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. <br />

Vivamus pretium et sapien quis condimentum. Duis facilisis dolor in nisl sagittis, et condimentum magna finibus. Donec ornare imperdiet arcu eget egestas. Nunc gravida arcu non risus imperdiet, eget faucibus ante elementum. Interdum et malesuada fames ac ante ipsum primis in faucibus. Aenean id eleifend turpis. Donec lacinia neque rhoncus, luctus enim eget, tempor elit. Nam sit amet imperdiet neque, ullamcorper ornare tortor. Cras eget metus ex. <br />


<p align="right">(<a href="#top">back to top</a>)</p>
<br />



<!-- FINDINGS -->
## Findings
<img src='./images/divskinny.png'><br />

```diff
- TO DO

- 1. BY DATE: Readme/Jupyter sections

- 2. BY DATE: Presentation

```

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. <br />

Vivamus pretium et sapien quis condimentum. Duis facilisis dolor in nisl sagittis, et condimentum magna finibus. Donec ornare imperdiet arcu eget egestas. Nunc gravida arcu non risus imperdiet, eget faucibus ante elementum. Interdum et malesuada fames ac ante ipsum primis in faucibus. Aenean id eleifend turpis. Donec lacinia neque rhoncus, luctus enim eget, tempor elit. Nam sit amet imperdiet neque, ullamcorper ornare tortor. Cras eget metus ex. <br />


<p align="right">(<a href="#top">back to top</a>)</p>
<br />


<!-- CONTACT CONTRIBUTORS -->
## Contact Contributors

Rowan Schaefer - [linkedin](https://linkedin.com/in/rowanschaefer) - [github](https://github.com/rowangayleschaefer) - rgscha02@gmail.com<br /> 


[Project Link](https://github.com/rowanschaefer/capstone)



<p align="right">(<a href="#top">back to top</a>)</p>
<br />




<!-- REQUEST A FEATURE -->
## Request a Feature

If you need a feature that isn't in here please open an issue and ask for it  <br />


<p align="right">(<a href="#top">back to top</a>)</p>
<br /></p>


<!-- CONTRIBUTING -->
## Contributing

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".
Don't forget to give the project a star! Thanks again!       <br />

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request


<p align="right">(<a href="#top">back to top</a>)</p>
<br /></p>







<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE.txt` for more information.

<p align="right">(<a href="#top">back to top</a>)</p>
<br />




<!-- ACKNOWLEDGEMENTS -->
## Acknowledgements

* Find orig source for this template
* Bullet
* Bullet

<p align="right">(<a href="#top">back to top</a>)</p>
<br />
 


<!-- blahblah -->
#### testing stuff
```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```

<br />


<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/rowangayleschaefer/covid_analysis.svg?style=for-the-badge
[contributors-url]: https://github.com/rowangayleschaefer/covid_analysis/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/rowangayleschaefer/covid_analysis.svg?style=for-the-badge
[forks-url]: https://github.com/rowangayleschaefer/covid_analysis/network/members
[stars-shield]: https://img.shields.io/github/stars/rowangayleschaefer/covid_analysis.svg?style=for-the-badge
[stars-url]: https://github.com/rowangayleschaefer/covid_analysis/stargazers
[issues-shield]: https://img.shields.io/github/issues/rowangayleschaefer/covid_analysis.svg?style=for-the-badge
[issues-url]: https://github.com/rowangayleschaefer/covid_analysis/issues
[license-shield]: https://img.shields.io/github/license/rowangayleschaefer/covid_analysis.svg?style=for-the-badge
[license-url]: https://github.com/rowangayleschaefer/covid_analysis/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/rowangayleschaefer
[product-screenshot]: images/screenshot.png

