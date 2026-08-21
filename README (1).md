# NYC Yellow Taxi Trip Analysis (June 2025)

A statistical analysis of NYC Yellow Taxi trip data, examining ride patterns,
fare behavior, vendor performance, and data quality — built around a real
regulatory question facing the NYC Taxi and Limousine Commission (TLC).

**Author:** Luisa Neira

## Research Question

Should the NYC Taxi and Limousine Commission (TLC) create a regulatory
mechanism to test the accuracy of the data provided by Taxicab Passenger
Enhancement Programs (TPEP) providers?

## Summary

From May 31 to June 30, 2025, NYC Yellow Taxi activity totaled over 4 million
trips, with demand heavily concentrated in central Manhattan and airport
routes (Queens) generating a disproportionate share of long-distance,
high-fare trips. Most rides were short — under 5 miles and less than 20
minutes — with volume peaking between 4-8 PM. Thursdays, Wednesdays, and
Mondays saw the highest weekday volume; Sundays led on weekends. Fares
clustered around $20, credit card remained the dominant payment method, and
the data showed a meaningful number of fare disputes and extreme outlier
values that can't simply be explained away.

A vendor-level comparison found that Curb Mobility (VendorID 2) had a
noticeably higher rate of negative fares and extreme high-fare outliers than
the other TPEP provider — the core evidence behind the project's audit
recommendation.

## What's in this analysis

- **Data cleaning:** timestamp conversion, missing value handling, duplicate
  checks, numeric field standardization
- **Univariate analysis:** trip distance, fare amount, passenger count,
  time-of-day and day-of-week distributions
- **Bivariate analysis:** correlation between trip distance and fare,
  passenger count vs. total fare, rate code relationships
- **Geographic analysis:** pickup/drop-off concentration by zone (Manhattan,
  Midtown, Times Square, Upper East Side as top areas)
- **Vendor comparison:** revenue distribution and data-quality differences
  between TPEP providers
- **Outlier & data quality review:** negative fares, extreme fare values,
  unrealistic trip distances

## Key findings

1. Taxi demand is strongly shaped by time and location — evening hours and
   central Manhattan dominate trip volume.
2. Trip distance and fare show a moderate positive correlation, consistent
   with NYC's distance-based pricing structure.
3. Passenger count and rate code have limited influence on total fare.
4. Revenue is concentrated in a small number of high-volume pickup zones.
5. **Curb Mobility (VendorID 2) shows a higher rate of negative fares and
   extreme high-fare values than the other vendor** — a data quality/
   compliance concern, not just noise.

## Recommendation

An audit or statistical review of vendor-reported data is warranted,
particularly for Curb Mobility (VendorID 2), given the frequency of
inexplicable extreme values in its reported fares.

## Data source

- [NYC TLC Trip Record Data](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page)
- [NYC TLC Data Dictionary – Yellow Taxi (2025)](https://www.nyc.gov/assets/tlc/downloads/pdf/data_dictionary_trip_records_yellow.pdf)
- [Taxi Zone Lookup Table](https://d37ci6vzurychx.cloudfront.net/misc/taxi_zone_lookup.csv)

The TLC states that trip data is provided by TPEP/LPEP technology providers,
not created by TLC itself, and TLC makes no representations as to its
accuracy — a detail directly relevant to this project's research question.

## Tools & libraries

`Python 3.x` · `pandas` · `NumPy` · `Matplotlib` · `Seaborn` · `Plotly` ·
`Jupyter Notebook`

## Repository contents

```
├── nyc_yellow_taxi_project.ipynb   # Full analysis notebook
└── README.md
```

## How to run

```bash
pip install pandas numpy matplotlib seaborn plotly jupyter
jupyter notebook nyc_yellow_taxi_project.ipynb
```

Trip data can be downloaded directly from the [NYC TLC Trip Record Data
page](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page) (June
2025 Yellow Taxi trip records).
