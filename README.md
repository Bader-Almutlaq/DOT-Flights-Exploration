# Flight Delay Data Exploration

This project investigates factors contributing to flight delays in the United States by analyzing a large dataset from the U.S. Department of Transportation (DOT). It includes exploring delay causes, analyzing patterns, and generating insights through data visualization and statistical analysis.

## Table of Content

- [Flight Delay Data Exploration](#flight-delay-data-exploration)
  - [Table of Content](#table-of-content)
  - [Project Structure](#project-structure)
  - [Features](#features)
  - [Datasets](#datasets)
    - [**Reporting Carrier On-Time Performance Data**](#reporting-carrier-on-time-performance-data)
  - [Process](#process)
  - [Technologies Used](#technologies-used)
  - [Requirements](#requirements)
  - [Instellation Instructions](#instellation-instructions)
  - [Usage](#usage)
  - [Results](#results)
    - [Summary of Findings](#summary-of-findings)
    - [Key Insights for Presentation](#key-insights-for-presentation)
  - [Acknowledgment](#acknowledgment)
    
## Project Structure

```markdown
Flight-Delay-Analysis/
├── DOT_Flights_Exploration.ipynb
├── DOT_Flights_Presentation.ipynb
├── DOT_Flights_Exploration.html
├── DOT_Flights_Presentation.slides.html
├── cleaned_airline.csv
├── airline_2m.zip
└── README.md
```

## Features

- Performs preliminary wrangling to clean and choose the most important features.
- Performs exploratory data analysis (EDA) on flight delay data.
- Visualizes patterns in delays based on different contributing factors.
- Identifies the most influential delay causes using statistical insights.

## Datasets

### **Reporting Carrier On-Time Performance Data**
- **Source**: [U.S. Department of Transportation (DOT)](https://www.transtats.bts.gov/DL_SelectFields.aspx?gnoyr_VQ=FGJ&QO_fu146_anzr=b0-gvzr)
- **Description**: Flight performance data, including delays and their causes, spanning 1987 to 2022. The dataset contains 2M records and 109 feature.
- **Features**:
  - A description of all the features is available [here](https://www.transtats.bts.gov/Fields.asp?gnoyr_VQ=FGJ)
  - The notebook focuses on this subset:
    ```code
    features = [

        # Time Features
        "Year", "Quarter", "Month", "DayofMonth", "DayOfWeek", "FlightDate", "CRSDepTime", "CRSArrTime",
        
        # Actual Departure and Arrival Times
        "DepTime", "ArrTime",
        
        # Delay and Duration Features
        "DepDelayMinutes", "ArrDelayMinutes", "CRSElapsedTime", "ActualElapsedTime", "AirTime", "Distance", "DistanceGroup",
        
        # Delay Causes
        "CarrierDelay", "WeatherDelay", "NASDelay", "SecurityDelay", "LateAircraftDelay",
        
        # Geographic Features
        "Origin", "Dest", "OriginStateName", "DestStateName"
    ]

    ```
  
## Process

1. **Data Preparation**:
   - Downloaded and cleaned the dataset.
   - Optimized data types to improve performance.
2. **Exploratory Analysis**:
   - Examined delay distributions and timing patterns.
   - Analyzed correlations between delay types and flight timings.
3. **Visualization**:
   - Created histograms, line plots, and scatter plots to highlight key insights.
4. **Presentation**:
   - Summarized findings in a presentation-ready format.

## Technologies Used

```
Python 3.x
pandas
numpy
matplotlib
seaborn
jupyter notebook
```

## Requirements

- Python 3.x installed.
- Install required libraries via pip or conda:
  ```bash
  pip install pandas numpy matplotlib seaborn jupyter
  ```
  
  ```bash
  conda install -c conda-forge pandas numpy matplotlib seaborn jupyter
  ```

## Instellation Instructions

1. Clone this repository:
   ```bash
   git clone <repository_url>
   ```
2. Ensure all dependencies are installed.
3. Download the required dataset:
   - The dataset can be found [here](https://www.transtats.bts.gov/).
4. Extract the dataset and place it in the project folder.
5. Open the Jupyter notebooks to explore the analysis:
   - `DOT_Flights_Exploration.ipynb`
   - `DOT_Flights_Presentation.ipynb`

## Usage

Run the Jupyter notebooks to explore flight delay data and generate insights:
```bash
jupyter notebook DOT_Flights_Exploration.ipynb
```

For presentation purposes, view:
```bash
jupyter nbconvert DOT_Flights_Presentation.ipynb --to slides --post serve
```

## Results

### Summary of Findings

In this exploration, I found that carrier delays were the most significant contributor to both departure and arrival delays, showing the highest correlation with `DepDelayMinutes` and `ArrDelayMinutes`. This suggests that operational issues such as maintenance or crew availability are often to blame for delays.

I observed interesting patterns related to the time of day. Delays were most frequent in the early morning hours, particularly between 3 AM and 5 AM, likely due to lower staffing levels and operational inefficiencies. As the day progressed, delays decreased, indicating better operational performance during peak hours.

In terms of flight duration, shorter flights tended to have more delays, possibly due to operational bottlenecks at smaller airports or reduced turnaround time. 

Outliers in both departure and arrival delays revealed that long delays, while rare, had a significant impact on the overall delay averages. These outliers may warrant further investigation for deeper insights.

Additionally, I found strong time-of-day patterns in delays, with the early morning hours seeing the highest delays, and these trends varied based on both departure and arrival times.

### Key Insights for Presentation

For the presentation, I will focus on the main factors contributing to flight delays:

1. **Distribution of Delays**: I will highlight the distributions of both departure and arrival delays to showcase the frequency and spread of delays.
   
2. **Time of Day**: The early morning delays will be emphasized, with insights into the operational inefficiencies that may contribute to these patterns.
   
3. **Carrier Delays**: The role of carrier delays in operational issues will be underscored as the most significant contributor to delays.


## Acknowledgment
- This project is part of [Udacity's](https://www.udacity.com/) *Data Analyst Nanodegree*

   


