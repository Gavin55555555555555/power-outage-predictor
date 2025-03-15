## Introduction 

| Column                    | Description                                                                                             |
|:--------------------------|:--------------------------------------------------------------------------------------------------------|
| `YEAR`                    | Year which the power outage occured.                                                                    |
| `MONTH`                   | Month which the power outage occured.                                                                   |
| `U.S._STATE`              | State where the power outage occured.                                                                   |
| `NERC.REGION`             | The North American Electric Reliability Corporation (NERC) regions involved with the power outage.      |
| `CLIMATE.REGION`          | US climate regions as specified by National Centers for Environmental Information.                      |
| `OUTAGE.START.DATE`       | Date when the power outage started.                                                                     |
| `OUTAGE.START.TIME`       | Time of day when the power outage started.                                                              |
| `OUTAGE.RESTORATION.DATE` | Date when power was restored to all customers.                                                          |
| `OUTAGE.RESTORATION.TIME` | Time of day when power was restored to all customers.                                                   |
| `CAUSE.CATEGORY`          | Category of event that caused the power outage.                                                         |
| `CAUSE.CATEGORY.DETAIL`   | Detailed description of the event that caused the power outage.                                         |
| `OUTAGE.DURATION`         | Duration of power outage in minutes.                                                                    |
| `TOTAL.CUSTOMERS`         | Annual number of total customers served in the US state.                                                |
| `UTIL.CONTRI`             | Utility industry׳s contribution to the total Gross State Product in the State.                          |
| `POPULATION`              | Population in the US state where the outage occured during the year the outage occured.                 |
| `POPPCT_URBAN`            | Percentage of the total population of the US state represented by the population of the urban clusters. |
| `POPPCT_UC`               | Percentage of the total population of the US state represented by the urban population.                 |
| `POPDEN_URBAN`            | Population density of the urban areas (persons per square mile).                                        |
| `POPDEN_UC`               | Population density of the urban clusters (persons per square mile).                                     |
| `POPDEN_RURAL`            | Population density of the rural areas (persons per square mile).                                        |
| `PCT_LAND`                | Percentage of land area in the US state as compared to the overall land area in the continental US.     |

## Data Cleaning and Exploratory Data Analysis
### Data Cleaning

|   YEAR | U.S._STATE   | OUTAGE.START        | OUTAGE.RESTORATION   |   OUTAGE.DURATION |   PROP_STATE_SERVED | IS_NIGHT   | SEVERITY   |
|-------:|:-------------|:--------------------|:---------------------|------------------:|--------------------:|:-----------|:-----------|
|   2011 | Minnesota    | 2011-07-01 17:00:00 | 2011-07-03 20:00:00  |              3060 |            0.485347 | False      | extreme    |
|   2014 | Minnesota    | 2014-05-11 18:38:00 | 2014-05-11 18:39:00  |                 1 |            0.483906 | True       | minor      |
|   2010 | Minnesota    | 2010-10-26 20:00:00 | 2010-10-28 22:00:00  |              3000 |            0.487093 | True       | extreme    |
|   2012 | Minnesota    | 2012-06-19 04:30:00 | 2012-06-20 23:00:00  |              2550 |            0.484498 | True       | average    |
|   2015 | Minnesota    | 2015-07-18 02:00:00 | 2015-07-19 07:00:00  |              1740 |            0.487018 | True       | average    |

### Univariate Analysis
<iframe
  src="plotly_graphs/univariate-analysis.html"
  width="800"
  height="600"
  frameborder="0"
></iframe>

### Bivariate Analysis
<iframe
  src="plotly_graphs/bivariate-analysis.html"
  width="800"
  height="600"
  frameborder="0"
></iframe>

### Interesting Aggregates

|   2000.0 |    2001.0 |   2002.0 |   2003.0 |    2004.0 |   2005.0 |   2006.0 |   2007.0 |    2008.0 |   2009.0 |   2010.0 |   2011.0 |   2012.0 |   2013.0 |    2014.0 |   2015.0 |    2016.0 |
|---------:|----------:|---------:|---------:|----------:|---------:|---------:|---------:|----------:|---------:|---------:|---------:|---------:|---------:|----------:|---------:|----------:|
|     0    |   494     |    0     |  520.167 |  268.4    |   145    |   159    |  317.833 |   360.222 | 8624.8   |   330.6  |   13.5   |  105     |  292.5   |     0     |    0     |     0     |
|     0    |     0     |    0     |    0     |    0      |     0    |     0    | 1676     | 17578.3   | 6570     |  9660    | 8265     | 6487.5   | 7624.33  | 22617.7   |  255     | 34072     |
|     0    |     0     |    0     | 1329.5   |    0      |     0    |     0    |    0     |     0     |    0     |     0    |  534.802 |  280.124 |  341.113 |   743.045 |  213.293 |   471.269 |
|     0    |     0     |    0     |    0     |    0      |     0    |     0    |   47     |   308.5   |  380.25  |   111    |  346.667 |   58.5   |  239.857 |    56     |  146.75  |   223     |
|     0    |   256.333 |    0     | 1548     | 3559.29   |     0    |   357    | 2430.5   |  6057.5   |  384     |  1351.57 | 1648.62  | 1020.67  |    0     |   570.4   |  336.75  |     0     |
|  3783.33 | 10140     | 5991     | 6299.47  | 5064.96   |  6047.94 |  4015.09 | 2896.3   |  5065.12  | 3905.22  |  3763.82 | 3139.36  | 4127.62  | 2678.92  |  1426.37  | 2123.08  |  1640.4   |
|   727.5  |   711.778 |  204.333 | 2528.57  |   96.3333 |   228.75 |   229    |  459.25  |   382.143 |  229.333 |  2112.85 |  579     |  330.429 |  160.333 |    52     |  375     |   947.125 |

<iframe
  src="plotly_graphs/interesting-agg.html"
  width="800"
  height="600"
  frameborder="0"
></iframe>

## Assessment of Missingness 

### NMAR Analysis
### Missingness Dependency

#### Missingness of Outage Duration depedent on Percent Land
<iframe
  src="plotly_graphs/missingness-analysis-pct-land.html"
  width="800"
  height="600"
  frameborder="0"
></iframe>

#### Missingness of Outage Duration depedent on State Population 
<iframe
  src="plotly_graphs/missingness-analysis-population.html"
  width="800"
  height="600"
  frameborder="0"
></iframe>

## Hypothesis Testing
<iframe
  src="plotly_graphs/hypothesis-testing.html"
  width="800"
  height="600"
  frameborder="0" 
></iframe>

## Framing a Prediction Problem


## Baseline Model

## Final Model

<iframe
  src="plotly_graphs/confusion-matrix.html"
  width="800"
  height="600"
  frameborder="0"
></iframe>

## Fairness Analysis 

<iframe
  src="plotly_graphs/fairness-analysis.html"
  width="800"
  height="600"
  frameborder="0"
></iframe>

