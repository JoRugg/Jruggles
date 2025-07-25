---
layout: post
title: "Personal and Public Transit Access Comparison - San Diego, California"
categories:
    - Projects
tags:
    - GIS
    - Urban Planning
published: true
comments: false
excerpt_separator:  <!--more-->
---

With this spring quarter being the last of my time at UCSD, this final GIS project marks my final, final project of my undergraduate education. With all the advanced tools of ArcGIS I learned how to use throughout the past 10 weeks, I wanted to continue experimenting with the Network Analysis tools to further indulge my curiosity and interest in transportation planning. I was quick to discover the complexity and resource intensity of these tools, so I decided to scale back my project ambitions from a comparison of different transit networks' service areas across the U.S., to a comparison of the transit and driving service areas in San Diego only, specifically regions served predominantly by the Metropolitan Transit System (MTS) network.
<!--more-->

The basis of my project and analysis relies on the ArcGIS Online Service Area Analysis Layer, a robust built-in network analysis layer for driving and pedestrian analysis. Beyond that, data collection was relatively minor compared to previous GIS projects, primarily focusing on municipal boundaries to improve the accuracy of the simulated network. From [SanGIS](https://geo.sandag.org/portal/apps/experiencebuilder/experience/?id=fad9e9c038c84f799b5378e4cc3ed068&page=Home), I gathered shapefiles for roads to build the network, municipal boundaries to remove regions not served by MTS, and finally bays and military facilities to serve as barriers that could not be origins, destinations, or routes for the network. I also used [MTS](https://www.sdmts.com/business-center/app-developers) scheduling data to facilitate simulating the transit network in the network analysis.

![Service Area Analysis of Public Transportation in San Diego, California Poster]({{site.baseurl}}/assets/images/SanDiegoTransitAnalysis.jpg)

The bulk of the workload came in setting up the network, starting with the Connect Public Transit Data Model to Streets tool to snap the bus stops of the MTS network to the streets. To ensure bus stops connected to pedestrian accessible roads, I added a flag to the road network indicating which roads were inaccessible, such as interstate freeways, to filter out of the process. With the MTS network connected to the road network, I created a transit network dataset from a template courtesy of [this tutorial](https://pro.arcgis.com/en/pro-app/latest/help/analysis/networks/create-and-use-a-network-dataset-with-public-transit-data.htm).

Next I needed to sample the region to serve as various origin points for the service area analysis. Unsure of how to best approach the sampling I opted to start with a random sampling of points across the entire county. However, I quickly found out that a majority of points were in remote, rural areas. To better represent the population distribution, I tried sampling 25 random points per municipal district. This approach revealed a new problem, in that smaller, independent municipal districts were both overrepresented and could not contain a full set of 25 evenly distributed points, while the city of San Diego was relatively sparse by comparison.

I was quickly running out of time on this project, with limited knowledge or guidance of other sampling methods, so I committed to the method of 25 random points per municipality. In the current state, the random sampling was inaccurate due to the span of the shapefile of San Diego County, which included waterways and military bases. So after clipping the region to exclude the invalid locations, I ran the sampling tool, and removed a few points that still generated in inaccessible places. With all the setup completed, I could finally begin the service area analysis, computing the service area accessible from the sample points within 15 minutes of driving and public transit. 

To compare municipalities, I took a summation of each sample point's service area, counting it towards a given municipality if the center of the shape, ideally the sample point itself, exists within the municipality. This approach did not exactly work as intended for the driving network, since small regions like Coronado and Imperial Beach lack land area to receive most of the count, especially compared to the neighboring city of San Diego. As a result, the graph is rife with outliers, jeopardizing the reliability of the analysis and results.

![Chart Summing Driving Service Area by Municipality]({{site.baseurl}}/assets/images/ServiceAreaDriving.jpg)

On top of that, the transit service area simply does not compare to the driving service area, differing by up to 3 orders of magnitude. With such a large disparity, no reasonable conclusions about the reliability of the transit network can be made. Additionally, a 15-minute service area creates a favorable bias towards driving, since the study does not account for time spent traveling to and waiting for transit stops, which can take up to 15 minutes itself. As a result, much of the transit network is not covered by the network analysis unless a random point happens to be near a transit stop with a bus arriving soon.

![Chart Summing Transit Service Area by Municipality]({{site.baseurl}}/assets/images/ServiceAreaTransit.jpg)

While this project did not necessarily produce useful or reliable results, I can say that I'm walking away with a better understanding of the tools I used to create the final poster. Given more time, experimentation, and some guidance from previous studies or community efforts, a similar study could serve as vital data to analyze the potential improvements of additional routes or increased frequency to the current transit network.

I could also imagine the original idea of expanding this study to cities across America being realized by finding a way to streamline the process of collecting the street and transit network data, creating the network analysis layers, and running the service area analysis. I myself would not know where to start on streamlining these steps, but perhaps I might start with a tutorial and template network dataset similar to the one I tried using in this project as a starting point for repeat studies. Finding a way to include historic and real time transit network and traffic data, while resource intensive, can aid in better analyzing service area during peak and off-peak times of the day, offering an even greater amount of data for transit agencies looking to expand their networks. 

While this study did not meet my initial expectations, and the results of the scaled back project did not lead to any reliable or insightful conclusions, I believe in the potential of the project, whether it's automating the process of creating network datasets for other cities, or creating an online dashboard to incorporate real-time data. I just wish I had more time and tools to work on this project and allow my ideas to truly come to fruition. For now, I'm walking away with more knowledge than I started, and I hope I can continue to learn the ins and outs of this software, as it has proven to offer much more than I was able to learn in the short span of a year.