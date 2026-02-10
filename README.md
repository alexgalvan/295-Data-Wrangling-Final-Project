**US Macroeconomic Data Analysis (2015–2025)**

Author: Alexander Galvan

Date: May 2025

Tools: R (tidyverse, ggplot2, rvest, rjson, etc)

**<br>Project Overview**

This project serves as a comprehensive data wrangling exercise focused on the "Dual Mandate" of the Federal Reserve: maintaining low unemployment and stable inflation. By stitching together disparate data sources—ranging from government APIs to web-scraped tables—the project visualizes how major geopolitical events (COVID-19, the Russia-Ukraine conflict, and trade policy shifts) impacted the US economy.

**<br>Key Features & Visualizations**

The analysis is broken down into several core economic pillars:

  The Stock Market (S&P 500): A 10-year trend analysis showing the resilience of the market despite significant pullbacks during historical crises.
  
  Interest Rates: A comparison of the Fed Funds Rate against Treasury Yield Curves (from 1-month to 30-year terms) to visualize how the Fed reacts to economic shifts.
  
  Unemployment & Inflation: National unemployment trends compared against the 3% "healthy" benchmark. Historical inflation rates versus the Fed’s 2% target.
  
  Consumer Price Index (CPI): A deep dive into the "CPI-U" (Urban Consumers) and a specific look at the volatility of Egg Prices.
  
  State-Level Employment: An animated choropleth map showing employment distribution across the US, plus a 2025 snapshot of the top 25 most employed states.
  
**<br>Data Sources**

The project utilizes a mix of static files, API calls, and web scraping:

    Category                        Source                                Method
    
    Stock Market                    NASDAQ (S&P 500)                      read_csv
    Treasury Yields                 US Treasury Department                read_csv & bind_rows
    Fed Funds                       FRED (St. Louis Fed)                  read_csv
    Inflation Rates                 US Inflation Calculator               rvest (Web Scraping)
    Employment/CPI                  Bureau of Labor Statistics (BLS)      blsAPI & rjson
    Geospatial Data                 tigris R Package                      sf objects
    
<br>**Technical Highlights**

  API Integration: Uses the blsAPI to fetch real-time government data.
  
  Complex Unpacking: Employs do.call and map functions to traverse nested JSON structures returned by the BLS.
  
  Data Reshaping: Extensive use of pivot_longer and left_join to align different time-series data on a single axis.
  
  Animation: Uses gganimate to show the temporal shift in state employment across the US map.
  
<br>**Setup & Dependencies**
  
  To run the .Rmd file, you will need an active BLS API key stored in a file named bls_api_key.R. The following libraries are required:
  
    library(tidyverse)
    library(rvest)   
    library(blsAPI)
    library(rjson)
    library(gganimate)
    library(viridis)
    library(tigris)
    
Note: This project was developed with troubleshooting assistance from ChatGPT for complex list traversals and JSON unpacking.
