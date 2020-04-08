---
layout: post
title: A note of a virtual conference on AI & CoViD-19 - Section 3
description: Organized by HAI (Stanford U) 1/4.
summary: Organized by HAI (Stanford U) 1/4.
tags: [summary, note, book]
---

Full Agenda: [HAI Stanford](https://hai.stanford.edu/events/covid-19-and-ai-virtual-conference/agenda)

Full video: [Youtube](https://www.youtube.com/watch?v=z4105Exe23Q)

**Edit** (8/4/2020) I add 4 more sections.

# Session III: Tracking the Epidemic - 3:01:45

## Taiwan’s Use of Data Analytics to Control COVID-19

*   Based on the JAMA paper on 3 Mar 2020.
*   How Taiwan prepares for the next crisis starts with the Communicable Disease Control Act.
*   How Taiwan designed a center command center with three databases: Insurance stockpile systems, Infectious Disease Stat System, and media surveillance.
*   In the first 30 days, how Taiwan recognized the crisis, including boarding people from Wuhan and the command center.
*   Linked dataset for big data analytics between insurance and immigration.
*   Government stockpile: 44M surgical mask, 1.0M N95.
*   Diamond Princess ship story.
*   Mobile app to track inventories for masks.
*   Infrared temperature map.
*   Communication and Politics.
*   Challenge for Taiwan.

## Tools for Estimating Unreported Infections of COVID-19

*   Pathengon Genomics and mathematical models
*   Why is undetected infection important? Asymptomatic or subclinical infection, limited testing capacity, restricted criteria for testing.
*   Consequence: spreading without notice, impacted large regions, longer time to elimination.
*   How to estimate: Mass testing, but expensive and time consuming; modeling; viral genomic data.
*   An example of a viral genomic data by time series with Wuhan Data.
*   Lead to Recommendation of face mask use by CDC

## Methods for Real Time Mapping of COVID-19 Cases Worldwide

*   Started in late December. It is a challenge to create a visualization (health map) because of a lack of resources.
*   Solved by going to local news and China sources.
*   It needs an army of people to get data, not just by machine learning and web scraping. So people created a network of researchers and professionals for every single case around the globe > A risk and intervention.
*   An example of Baidu data about actions when you have detailed information.
*   An example of crowd source data from Thermia. Data connected to a medical device.
*   Symptom checkers with AI chatbot called Buoy. Other side, collect data to increase local surveillance.
*   Another flu near you to crowdsource data.
*   Another example with CoViD near you. 260 people reported symptoms.
*   Mining for social measure: to understand social distancing impact with collaboration with CDC, e.g. mapping data between policy and impact.

## Epidemiological Forecasting Tools for COVID-19

*   Flu background: Influenza and author story with connection with CDC
*   Flu prevalence data: Most target interest of CDC is % influenza like illness started in 1997. Data collected weekly. Why? Based on the severity pyramid.
*   How to forecast a season epidemic:
    *   Choose a type of model: mechanistic vs. statistical;
    *   For stat models, collects lots of data like Google search queries, Wikipedia page hits, thermometer sales, etc.
    *   For stat models, long history of training data to learn predictive relationships.
    *   Either type, should model revisions (backcasting!)
    *   Either type, prob forecasts are key; as are ENSEMBLEs.
*   How to not forecast a pandemic: SEASONAL epidemic
    *   Digital surveillance sensor > erratic model;
    *   Without sensors, ILI decreases.
*   Information about CDC flu forecast challenge about %ILC and hospitalization.
*   CMU effort in data challenge at [https://delphi.cmu.edu/crowdcast/](https://delphi.cmu.edu/crowdcast/)

## A mobile app intervention to slow COVID-19 using crowdsourced data

*   Shared a story of Wuhan quarantine along with a speaker’s acknowledgement about the scale, and how she started to know about the China virus tracking app with a concern about a pervasive data collection which is not accepted in the US.
*   GPS is perhaps a solution with anonymous data for contact tracing apps, which allows us to find individuals contacted by an illed person. The challenge is highly restricted information of medical data.
*   Talked about a tracking app for the flu by using bluetooth protocols which are localized, so can deconstruct data. It allows us not to collect data of a person to do intervention.
*   Bluetooth strength allows us to know about the proximity of the person between two people.
*   Some other teams also work on this topic: COVID watch, TraceTogether, PrivateKit: Safe Paths, Colgi: Community Epidemiology in Actions.


## AI for COVID-19: An online virtual care approach

*   Healthcare access and scalability with 50% world with no access to essential health service, ~30% of the US adults under-insured. ⅓ Americans self-diagnose online, ~15 minutes to capture information, diagnose and recommend treatment. COVID-19 is putting a huge stress on the medical system.
*   Problem of telehealth: it only solves some problems, importantly can NOT SCALE.
*   A proposal towards AI powered scalable health systems with a human in the loop, mobile first care.
*   A demo of how it looks in practice (chat-based application) with client side and doctor side.
*   An example of UI for Personalized diagnostic assessment.
*   Some peer-reviewed research about diagnosis with an example of question similarity with automated question and answering & feedback loop. But it is hard to verify because of lacking ground truth.


## Knowledge technology to accelerate open science in addressing the COVID-19 pandemic

*   COVID-19 will change science and the way we do science.
*   10-20 years change drastically with data and hypothesis. There is a shift from output science, but science. Data of COVID-19 becomes available leading to excitement.
*   Problem is that there is too much data without a catalog which does not have a catalog.
*   The point to make: Open data is about more than disclosure. It must be fair, findable, accessible, interoperable, reusable. Nevertheless most of the data is not fair.
*   Example of a failure to use standard terms makes datasets often impossible to search. E.g. name of variables (age, Age, AGE, ‘Age, age (after birth), age (in years), age(y), age[y], age[years])
*   Another example of bad meta data from NCBI BioSample 73% of “Boolean” metadata values are not actually true or false; 26% of data can not be parsed into integers, 68% of metadata entries that supposed represent terms from standard vocabularies do not actually do so.
*   Why does it matter? To find data from relevant studies, integrate new results, re-explore existing data and verify published samples.
*   Solution: CEDAR approach to standardize Metadata with three step process.
*   An application of a use of CEDAR with project VODAN to help researchers learn about epidemic.
*   Online data will never be fair until we standardize metadata with templates&lt;-controlled terms&lt;-technology that makes it easy for investigators to annotate their datasets in standardized and searchable ways.


## What we can learn from Twitter Analysis about COVID-19

*   The psychological impact of COVID-19: uncertainty/ anxiety, unemployment and loneliness -> The path of well-being and mental health.
*   Unemployment and life satisfaction: job loss highest rate ever since the WWII
*   Digital social transition might be a solution for loneliness.
*   Introduction to do text analysis on twitter nationwide of the US. Scraping data on 26/2-26/3 in 2015 counties: Urban counties Washing your hands, panic buying, work from home, canceled events, wash hands; Educated counties: Government, healthcare, articles/ news, will be canceled, testing; Older counties: Trump and economic impact; Younger counties: wash hands; Voted for Trump: like the flu; Most negative sentiment: Scared, Economy, Trump;
<!-- Docs to Markdown version 1.0β21 -->
