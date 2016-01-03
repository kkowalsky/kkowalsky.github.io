---
layout: blog
type: blog
title: Your Body, (Not) Your Choice
---

<a href="http://twitter.com/tolomaps">Robin Tolochko</a>, <a href="http://twitter.com/dylanmoriarty">Dylan Moriarty</a>, and I have been working on our geography 575: web mapping final project. Our map is about the changes in abortion legislation at the state level since Roe vs. Wade. We're making an interactive map with D3, jQuery, Twitter Bootstrap and Queue.js.

There's a ton that goes into this type of process and Robin, Dylan and I have spent a lot of time in person, via email, google drive, and github discussing the many components required for this map. We have a huge goal in mind: to create a map that illustrates the sweeping changes in abortion law and the rising tide of conservatism when it comes to issues strictly related to a woman's body.

![Team](../../../../assets/img/blog/team.jpg)

We started off with basic prototyping of what we wanted to include and how it was going to look. It's highly iterative, so we've made a couple of changes over time. The basic look is going to resemble something the New York Times would make; our friends<a href="http://twitter.com/erinhamilton"> Erin</a>, <a href="http://twitter.com/rashaunamead">Rashauna</a>, and <a href="http://twitter.com/runforfunner">Vanessa</a> made a similar <a href="http://50yearsofchange.com">map</a> on the history of LGBT laws in the past 50 years for their final project in the same class. We outlined clear divs (or sections): the intro, the map itself, the underlying graph(s), the data analysis section, and about section.

Our first step? <strong>Getting data to map. </strong>

It's seems like an easy enough process: make a list of everything you need database, find the sources, download the shapefile or csv, and get going. If only this were the case. We had to gather this data all by hand from a bunch of different resources like the Guttmacher Institute, NARAL, Planned Parenthood, and the National Abortion Federation. While Robin worked on her part of the data, gathering all the Crisis Pregnancy Center and Abortion Clinic locations (read her <a href="http://tolomaps.tumblr.com/post/104104145998/interactive-cartography-final-project-data">blog</a> about it!), Dylan and I studied the legislative changes.

I thought this was gonna be a lot of reading of books, studying laws at the library, but it turned out to be the hardest part of the process. While Robin had to struggle geocoding every location, we had to outline all the legislative data for every states since 1973. This is super hard to find, because every book I read had specific examples of historical laws or only the laws currently on the books. After a few days of struggling, I discovered<a href="http://www.prochoiceamerica.org/government-and-you/state-governments/"> NARAL's state center</a> that showed the current laws on the record:


![](../../../../assets/img/blog/abortionmap.png)

Clicking through to each state provided all the various restrictions and had the years enacted and amended. It was hard going through each state, but eventually I made the basic database. From there, we had to get the years they were implemented and made a separate spreadsheet. To actually code this in d3, we need to make another set of spreadsheets with each policy and have the policies in effect for each year listed. An example below shows one of our spreadsheets in the middle of being completed. Basically, once it gets implemented, the popup has to show that value in the spreadsheet for every consequent year (unless it gets changed or enjoined).

![](../../../../assets/img/blog/googlesheets.png)

&nbsp;

After making individual csvs in google drive, I exported them and put them in our data folder to be loaded in our main.js file.

Part II coming soon!