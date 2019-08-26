# Video-Games-Project
> Analysis of video game trends over the last 50 years. 

## Table of contents
* [Motivation](#motivation)
* [General info](#general-info)
* [Screenshots](#screenshots)
* [Technologies](#technologies)
* [Setup](#setup)
* [Features](#features)
* [Status](#status)
* [Inspiration](#inspiration)
* [Contact](#contact)

## Motivation 
One of the main branches of the entertainment industry is video games. Our group decided to investigate this area to look for exciting correlations and trends in that industry. The proposed research is based on a dataset of 167,000 video games with a detailed description of each. The purpose of this study is to find a pattern and correlation between ratings of the games, popularity, platforms, genres, and developers. 

## General info 
The project consisted of 3 main parts: deliverable #1, deliverable #2 and final report. In the first one, our team looked into the variation of one and more variables to spot some interesting findings and correlations. In the second deliverable we fitted a linear regression model, tested some hypotheses and plotted the predictions of our response. In the final report we summarized our findings and concluded how trends of video games differed over time and what affected those trends.


## Technologies
* R Studio - Version 1.1.463

## Setup
Describe how to install / setup your local environement / add link to demo version.

## Code Examples
Show examples of usage:
`library(tidyverse)
data <- read_csv("vgsales_metacritic.csv", col_types =  cols(Critic_Score = col_double(), User_Score = col_double()))

data_filtered <- data %>% filter((Global_Sales != 0 | Total_Shipped != 0) &!is.na(User_Score) & !is.na(Critic_Score)) %>% mutate(Sales = Global_Sales + Total_Shipped, Sales_log = log(Global_Sales + Total_Shipped), Log_CS = log(Critic_Score), Log_US = log(User_Score))
problems(data_filtered)

data_filtered %>% mutate(density_th = dnorm(log(Sales), mean = mean(log(Sales)), sd = sd(log(Sales)))) %>% 
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
       The red line is the theoretical normal distribution of Sales.") 
`

## Status
Project is: _finished_

## Contact
Created by Abdulshaheed Alqunber, Rami Bassil, Ekaterina Gorbunova, Khalid Khumayis - feel free to contact me at eginfo@bu.edu!
