---
layout: blog
type: blog
title: Immigration Action Maps
---

Last night, President Obama announced his plan for an executive action on immigration. Politics aside, any major event like this calls for every major news outlet to make a map, much to my delight. Here's a roundup of the first I found the day after the address and how I feel about them.

<a href="http://www.nytimes.com/interactive/2014/11/20/us/2014-11-20-immigration.html?hp&amp;action=click&amp;pgtype=Homepage&amp;module=first-column-region&amp;region=top-news&amp;WT.nav=top-news" target="_blank">New York Times:</a>

<a href="https://kowalskycartography.files.wordpress.com/2014/11/screen-shot-2014-11-21-at-10-06-57-am.png"><img class="alignnone wp-image-61 size-large" src="https://kowalskycartography.files.wordpress.com/2014/11/screen-shot-2014-11-21-at-10-06-57-am.png?w=656" alt="New York Times " width="656" height="234" /></a>

Way to go, NYT on being the first graphs and charts I saw. They also didn't use the same dataset in the same choropleth state map that everyone else did. Their graphic analysis of this was of superb quality, per usual. It's easy to always want to map data (says the cartographer), but may not be the easiest way to convey information to people. Instead, the New York Times made a series of graphs and charts outlining <strong>who</strong> this executive action is really helping, <strong>how</strong> illegal immigration has been changing in the recent years, and <b>what</b> Americans feel about it.

The only thing missing? The<strong> where</strong>. Perhaps that's good, seeing as they are also focusing on an important factor of this issue, which is how Americans feel about it. I know how the GOP is gonna feel, and don't care to listen to the trench warfare of partisan politics. I'm interested in seeing how people actually feel about immigration, and using these simple charts is a clear way to cut through the map reading errors and straight to the good stuff.

<a href="http://www.washingtonpost.com/blogs/the-fix/wp/2014/11/21/the-impact-of-obamas-immigration-executive-action-state-by-state-in-1-map/?hpid=z2&amp;Post+generic=%3Ftid%3Dsm_twitter_washingtonpost" target="_blank">Washington Post:</a>

<a href="https://kowalskycartography.files.wordpress.com/2014/11/screen-shot-2014-11-21-at-10-04-22-am.png"><img class="alignnone wp-image-62 size-full" src="https://kowalskycartography.files.wordpress.com/2014/11/screen-shot-2014-11-21-at-10-04-22-am.png" alt="Washington Post" width="574" height="371" /></a>

This one's my least favorite and I'm switching to bullet point to explain why:
<ul>
	<li>IT'S TOO SMALL. Yeah, this is a supportive feature of their article, but their svg is drawn in a way that could have allowed for a substantially larger map. My rule of thumb? If you're going to add a map, even as a supplement, you need it to be able to be easily read.</li>
	<li>It takes too long too load (hey dude, what kinda weird script do you have in there?)</li>
	<li>Hawaii and Alaska sink too far back in the visual hierarchy. I couldn't actually tell Hawaii was include for a second.</li>
	<li>Is this even projected? It might be Mercator, but I know this isn't US Albers which is built into D3 and thus SUPER easy to add. Also D3's projection features might have helped with the scale issues.</li>
	<li>The highlighting is pretty faint. Now I get for design considerations to maybe make this soft, but this is just too low. Especially for the size.</li>
	<li>Adding a legend might not be as fast, but it allows the reader to see the breakup of these classes.</li>
</ul>
However, kudos to them for normalizing their data by using percents. It didn't fix the overall implementation issues, but i'm glad someone really took that into consideration. Don't get me wrong, I really like the Washington Post, but I've never been astounded by their graphics and wasn't surprised at the 'okay-ness' of this map.

<a href="http://time.com/3598582/map-obama-immigration-action/" target="_blank">Time Magazine:</a>

<a href="https://kowalskycartography.files.wordpress.com/2014/11/screen-shot-2014-11-21-at-10-05-16-am.png"><img class="alignnone wp-image-64 size-full" src="https://kowalskycartography.files.wordpress.com/2014/11/screen-shot-2014-11-21-at-10-05-16-am.png" alt="Time" width="608" height="486" /></a>

Alright, this is already much better than the previous one. They add an affordance for their readers to tell them to mouseover for the data, their legend is well defined, the size fills the width of the article, you can see Alaska and Hawaii. I especially am glad they included all 50 states in the color ramp.

My only concern about this map is the lack of normalization and use of raw figures, which is bad because eyes tend to focus on things that are larger even if they're lower in color value than something smaller but brighter. At the same time though, the states that are important in this conversation are California, Texas, and other Western States. However, if you look at the Washington Post map, you see that Utah appears to be a lot more important than Time's map would have you think. It's evident that Time wanted to discuss the sheer numbers of people affected, but sigh. Normalizing for choropleth maps is pretty important, but you know, whatever.

<a href="http://www.bostonglobe.com/news/nation/2014/11/20/congress-will-act-stop-obama-immigration-mcconnell-says/mkf7XuzhvVsbnnRieyXDRL/igraphic.html?p1=Article_Graphic" target="_blank">Boston Globe:</a>

<a href="https://kowalskycartography.files.wordpress.com/2014/11/screen-shot-2014-11-21-at-10-10-58-am.png"><img class="alignnone wp-image-65 size-large" src="https://kowalskycartography.files.wordpress.com/2014/11/screen-shot-2014-11-21-at-10-10-58-am.png?w=656" alt="Boston Globe" width="656" height="458" /></a>

&nbsp;

I stumbled upon this map from the Boston Globe about #ImmigrationAction and was surprised. Normalized data? check. Color scale with adjacent legend? check. The only thing I found wrong with this map is the data itself. All of the other maps used data from the Migration Policy Institute. The American Community Survey is part of the US Census and this data only examines how many people in each county aren't US citizens, not whether or not they're here illegally.

The subtitle of this map states "About 490,000 people in Massachusetts are not classified as US citizens, according to the 2012 American Community Survey. Here is where they live." That's all fine and dandy to report on any other day of the year, but it's wrong. Especially for discussing Obama's Immigration Action. The Migration Policy Institute says the figure of illegal immigrants in Massachusetts is actually about <a href="http://migrationpolicy.org/data/unauthorized-immigrant-population/state/MA" target="_blank">185,000</a>. This is just plain irresponsible, because unless the reader of the Globe knows a lot about the ACS, it's unlikely they're realizing that this isn't about illegal immigrants, which was the focus of this executive order. Good try though!