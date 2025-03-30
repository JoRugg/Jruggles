---
layout: post
title: "Colorado Wildfire Risk Assessment"
categories:
    - Projects
tags:
    - GIS
    - Urban Planning
    - Projects
published: true
comments: false
excerpt_separator:  <!--more-->
---

For the second and final project of the introductory GIS class, we were given a much more open-ended task of answering a research question of our choice, with the freedom to choose our own topic and a long list of available resources and data. With my assigned state of Colorado and a 2 week deadline, I wanted a topic both relevant and familiar. Given the urgency of climate change and its manifestation in the form of wildfires across my home state of California and the rest of the U.S. West Coast, I wanted my research question to focus on the links between air pollutants as a cause of more severe wildfires as a result of global warming and drier climate. However, the data I planned to use was not formatted correctly for ArcGIS. In this case, the availability of data influenced the question itself, transforming the question to asking if there exists a causal link between wildfire location, frequency and severity on the local population and air quality throughout the year 2023. <!--more-->

To help answer my new research question, I sourced wildfire data from the [National Risk Index](https://hazards.fema.gov/nri/data-resources) (NRI), air quality indicators from the [Environmental Protection Agency](https://www.epa.gov/outdoor-air-quality-data/air-quality-index-report) (EPA), and fire prevention data from the [Bureau of Land Management](https://gbp-blm-egis.hub.arcgis.com/datasets/BLM-EGIS::blm-co-completed-vegetation-treatments-polygons/about) (BLM). I would quickly learn that the bulk of my time on this project would be spent trimming the data I selected to minimize the time spent running analysis tools and best aid in answering my research question. 

From the NRI data, I chose to isolate wildfire frequency and population exposure, summarizing points by county and mapping the relationship on the map below. Taking a sample of 5 counties with either a high population exposure, high wildfire frequency, or both, I graphed the changes in air quality over time as measured by the EPA. No GIS analysis tools were actually necessary to portray the EPA data, beyond some trimming necessary to display the charts without too much noise. Taken together, the notable spike in the air quality rating during peak wildfire season of the late summer months suggests a positive correlation between wildfire frequency and severity on air quality.

![Wildfire Frequency and Population Exposure]({{site.baseurl}}/assets/images/ColoradoAirQuality.jpg)

Transitioning away from the devastation of wildfires, the following map highlights preventative efforts with data from the Bureau of Land Management focusing on fire prone areas which have undergone treatment in the form of controlled burns and other non-destructive methods. Overlaying the total acres of prescribed treatment on top of the normalized wildfire exposure area, it is evident that prescribed treatment occurred predominantly in West Colorado, while many fire prone counties are in the east of the state. Without an indication of whether the treatments preceded or followed the wildfires, the map could indicate either the success of prescribed treatment at reducing wildfire exposure area, or the misplacement of treatment, as most fire prone counties received little to no treatment at all. The scatter plot below is another representation of this same data, categorizing data points by NRI resilience rating. Now, there's a loose correlation between the lack of treatment, and high resilience, suggesting counties resilient to or at low risk of wildfires are a lower priority candidate for treatment.

![Prescribed Treatments over Fire Prone Areas]({{site.baseurl}}/assets/images/ColoradoWildfireTreatment.jpg)

In hindsight, the research question seems relatively self evident, of course the increase in wildfires will result in worse air quality, and the most fire prone areas should be the first to receive preventative treatment. But not all research needs to be groundbreaking. There's value in research which reaffirms what we already know to be true, offering more evidence and insight for our decision makers to confidently tackle the changing climate of a rapidly changing landscape.

The conciseness of the maps in this project demonstrate a slight improvement from my previous midterm project, where I was struggling with the nuances of GIS. I recognize that the map and associated legends are difficult to parse, likely a result of trying to cram too much data on a single map, harming the readability of the maps to a general audience. But design was not a high priority in the original assignment. Still, improving the design of my works is a skill that I'm prepared to continue developing through practice. I'm becoming more familiar with the tools GIS provides to design and create meaningful visuals from data to effectively communicate findings and inform our decisions, and I'm interested in continuing learning how to use GIS in future academic and career opportunities.