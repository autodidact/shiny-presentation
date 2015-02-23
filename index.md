---
title       : Bombay Stock Exchange Historical Returns
subtitle    : A tool to investiage historical returns on BSE Index
author      : 
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## What is Bombay Stock Exchange?

1. Old Stock Market in Asia. Located in Mumbai.
2. We are going to track BSE 30 Index, an index made of 30 well established
companies listed on BSE.
3. Data available at [[http://www.bseindia.com/indices/indexarchivedata.aspx]]

--- .class #id 

## Why?

1. Most experts in economics say that stock market is a random process which is mathematically intractable.
2. In general, day to day movements are not predictable. 
3. On the other hand, stock market long term movements can be predicted and are more an indicator of developing wealth of a country. It will be useful to investigate whether simply following the stock index results in long term profilts.

--- .class #id 

## Dataset
The dataset contains 8185 days of stock market movement from April 1979 onwards.


```r
url <- getURL("https://raw.githubusercontent.com/autodidact/DataProductShiny/master/data/bse30.csv",encoding="UTF-8")
data <- read.csv(text=url)
data$Date <- as.Date(data$Date,format="%e-%B-%Y")
```


```r
plot(data$Date, data$Close)
```

![plot of chunk unnamed-chunk-3](assets/fig/unnamed-chunk-3.png) 

--- .class #id 

## Shiny Application

* The purpose of the application is how much money one would have made if we simply invested in the stocks in the BSE 30 Index. That might be a dumb strategy, but thats the idea.
* You can chose a starting date and investment interval. We assume units of 100 are invested at regular intervals.
* We get a plot of stock movement as well as the total invesment vs current value of the portfolio.
* Go give it a try at https://autodidact.shinyapps.io/shiny_stocks_india/

--- .class #id 
