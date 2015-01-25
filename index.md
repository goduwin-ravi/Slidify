---
title       : Developing Data Products
subtitle    : Course Project (Part-2) - Slidify
author      : Goduwin Ravi
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [bootstrap]   # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Agenda

  - Background/Motivation
  - Purpose & Objectives
  - Code for plots
  - Guidelines to reproduce locally

---

## Background/Motivation
This presentation is part-2 of the Developing Data Products course project which serves as the user guide to part-1 of the course project which contains the actual code for the shinyapps project.

The data set used is the default mtcars data set included in R

Launch the shinyapps project from:  https://goduwinravi.shinyapps.io/shinyapp/

---


## Purpose & Objectives
A tool to dynamically analyze mtcars data set. 
This tool should allow displaying data as graphs for a given selection parameter with an ability to:
  - dynamically subset the data by the number of cylinders (4,6, or 8) and
  - the type of transmission (Automatic or Manual).
  
These capabilities are available as "drop-down menu", "slider bar" and "radio button" interfaces

---

## Code for the plots

    # Generate a plot of the requested variable against mpg and  
    output$mpgPlot <- renderPlot({    

      # Filter display data as required by the user
      mpgData <- subset( mtcars, am==input$am & cyl==input$cyl )

      boxplot(as.formula(formulaText()), 
              data = mpgData,
              col = (c("red","blue"))) 
    })
    
You may launch the above code from:  https://goduwinravi.shinyapps.io/shinyapp/


Note: The complete code for the shinyapps project can be found at: https://github.com/goduwin-ravi/ShinyApp
      

