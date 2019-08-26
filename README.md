# Analyzing-Video-Games-Trends-Project
> Analysis of video game trends over the last 50 years. 

## Table of contents
* [Motivation](#motivation)
* [General info](#general-info)
* [Data description](#data-description)
* [Technologies](#technologies)
* [Code examples](#code-examples)
* [Status](#status)
* [Contact](#contact)

## Motivation 
One of the main branches of the entertainment industry is video games. Our group decided to investigate this area to look for exciting correlations and trends in that industry. The proposed research is based on a dataset of 167,000 video games with a detailed description of each. The purpose of this study is to find a pattern and correlation between ratings of the games, popularity, platforms, genres, and developers. 

## General info 
The project consisted of 3 main parts: deliverable #1, deliverable #2 and final report. In the first one, our team looked into the variation of one and more variables to spot some interesting findings and correlations. In the second deliverable we fitted a linear regression model, tested some hypotheses and plotted the predictions of our response. In the final report we summarized our findings and concluded how trends of video games differed over time and what affected those trends.

## Data description 
Initially, our group used dataset found on Kaggle created by a user named `Juttuga Rakesh`. However, in the middle of the project we realized that there was a lot of data missing data points (especially in the years following 2009) that ultimately resulted in faulty analysis. We searched for an updated version of the same dataset that at least includes the last year or two, but we could not find any. Therefore, we were able to backtrace the source code that used to scrape the data from VGChartz website to build an updated version of the dataset. Because the original dataset is about five years old, the code needed to be modified to make it work with the new structure of HTML document file and CSS style of the website. Eventually, we were able to build a new dataset that includes almost 56,000 games — a multiple of 3.5 in size of the original dataset.

## Technologies
* R Studio - Version 1.1.463

## Code Examples
Here is the first: 

  ` data_filtered %>% mutate(density_th = dnorm(log(Sales), mean = mean(log(Sales)), sd = sd(log(Sales)))) %>% 
    ggplot() + 
    geom_histogram(aes(x = log(Sales), y = ..density..), fill = "gray", color = "black", binwidth = 0.2) + 
    geom_density(aes(x = log(Sales)), colour = "blue", fill = "blue", alpha = 0.2) + 
    geom_line(aes(x = log(Sales), y = density_th), colour = "red") + 
    labs(x = "Log(Sales)", 
        y =  "Density", 
        title = "Sales Distribution", 
        subtitle = "Graph 7", 
        caption = "This graph showcases how close is the actual data relative to the theoretical distribution. 
        The blue line and its fill showcases the actual Sales' distribution. 
        The red line is the theoretical normal distribution of Sales.") `

## Status
Project is: _finished_

## Contact
Created by Abdulshaheed Alqunber, Rami Bassil, Ekaterina Gorbunova, Khalid Khumayis - feel free to contact me at eginfo@bu.edu!
