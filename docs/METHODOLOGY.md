# Methodology, Sources and Limitations

## 1. Research question and scope

This project describes how selected precious-metal prices evolved from January 2021 through December 2025 and compares their monthly returns with selected industrial metals. It also documents potential channels through which metal prices can affect downstream manufacturing costs.

The analysis is descriptive. It does not estimate causal effects, forecast prices or provide investment advice.

## 2. Price data

### World Bank source

The supplied monthly commodity workbook is used for gold, silver, platinum and the selected industrial-metal comparators (copper, aluminium and nickel). The observations are monthly benchmark averages. Precious-metal prices are expressed in nominal US dollars per troy ounce.

### Palladium supplement

Palladium is not present in the supplied World Bank monthly sheet used for this project. A separate monthly IMF Primary Commodity Prices (PCPS) series was transcribed from the published historical table and added as a supplementary series. Users should preserve this source distinction when extending the dataset.

## 3. Transformations

### Quarterly average

For each calendar quarter, the arithmetic mean of the three monthly observations is calculated.

### Quarter-over-quarter change

`QoQ (%) = (quarter average / previous quarter average - 1) × 100`

The first quarter in the sample has no prior-quarter comparison unless the preceding quarter is separately supplied.

### Price-level coefficient of variation

`CV (%) = sample standard deviation of monthly price levels / mean monthly price level × 100`

This measures dispersion relative to the mean price level. It is not the same as return volatility.

### Monthly returns and correlations

Monthly simple returns are calculated as `P(t) / P(t-1) - 1`. Pearson correlations are calculated across the monthly return series. Correlation indicates co-movement in this sample and does not establish causality or a stable structural relationship.

## 4. Macro indicators: planned, not populated

The workbook's `Macro_Series` worksheet lists candidate CPI and PPI indicators and official sources. It does **not** contain the underlying monthly CPI/PPI observations. Consequently, the project does not calculate:
- correlations between precious-metal prices and CPI/PPI;
- inflation-adjusted metal prices;
- lagged relationships between metal prices and producer prices;
- regression-based inflation or producer-cost pass-through.

For a defensible extension, retrieve a consistent monthly sample for each economy, document seasonal adjustment and index base conventions, transform indices to year-over-year rates where appropriate, align release calendars and dates, and report missing observations. Cross-country comparisons should account for differences in index definitions.

## 5. Industrial cost-transmission pathways

The workbook documents three conceptual pathways:

- **Jewelry:** metal procurement → refining/alloying → fabrication and finishing → jewelry producer prices.
- **Electronics:** conductive and contact materials → component manufacturing → electronic equipment producer prices.
- **Catalysts:** platinum-group metal procurement and substrate materials → catalyst formulation/assembly → catalyst, chemical or automotive output prices.

These are conceptual maps, not quantified models. A robust pass-through study would require industry-specific producer-price indices, input-output weights, labor and energy cost measures, exchange-rate controls and plausible time lags. A spot metal price is only one component of delivered manufacturing cost.

## 6. Data-quality caveats

- The series are nominal, not adjusted for inflation.
- World Bank and IMF series may differ in benchmark definitions, source conventions and revision practices.
- Monthly averages do not represent intramonth highs/lows or month-end settlement prices.
- In the current workbook/dashboard build, the monthly-return standard deviation and best/worst monthly return summary fields are decimal returns but their labels imply percentages. Multiply those fields by 100 before interpreting them as percentages. The price-level CV fields are already percentages. Recalculate from `Monthly_Data` for downstream use.
- The source workbook metadata may show a publication/update date that differs from the observation end date. The sample in this project runs through December 2025.

## 7. Suggested next steps

1. Load official monthly CPI and PPI observations for each selected economy.
2. Add harmonized year-over-year and month-over-month transformations.
3. Recalculate correlation matrices using aligned dates and explicit missing-data rules.
4. Estimate lagged models only after checking stationarity, structural breaks and multicollinearity.
5. Add industry-specific cost indices and input-output weights before estimating pass-through.
6. Add automated data validation and a reproducible refresh pipeline.
