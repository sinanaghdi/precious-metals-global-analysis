# Precious Metals Global Analysis (2021–2025)

An exploratory commodity-market analysis of **gold, silver, platinum and palladium**, with copper, aluminium and nickel used as industrial-metal comparators. The project brings monthly benchmark prices, quarterly changes, annual statistics, return correlations and conceptual industrial cost-transmission pathways into one downloadable workbook and an interactive dashboard.

> **Scope note:** This is a historical descriptive analysis, not an investment recommendation or a causal inflation study. The workbook identifies relevant CPI/PPI series but does not contain their monthly observations. The industry cost pathways are conceptual and are not estimated pass-through models.

## Project deliverables

- **Interactive dashboard:** [Open dashboard](dashboard/Precious_Metals_Dashboard_2021_2025.html)
- **Analysis workbook:** [Download Excel workbook](data/Precious_Metals_Global_2021_2025.xlsx)
- **Methodology and limitations:** [Read the methodology](docs/METHODOLOGY.md)

## Coverage

| Item | Coverage |
|---|---|
| Period | January 2021 – December 2025 |
| Frequency | Monthly benchmark averages |
| Precious metals | Gold, silver, platinum, palladium |
| Industrial comparators | Copper, aluminium, nickel |
| Price denomination | Nominal USD per troy ounce for precious metals |
| Main calculations | Monthly price trends, quarterly average QoQ changes, annual summaries, price-level coefficient of variation (CV), monthly-return correlations |
| Dashboard | Plotly-based HTML; Plotly is loaded from its public CDN |

## Dashboard contents

1. Monthly precious-metal price trends
2. Rebased price performance (January 2021 = 100)
3. Quarterly average price changes (QoQ)
4. Correlation heatmap of monthly returns
5. Price-level CV and monthly-return volatility summary
6. CPI/PPI indicator reference table and data-availability note
7. Conceptual industrial cost-transmission pathways
8. Annual metal statistics

## Workbook structure

| Worksheet | Contents |
|---|---|
| `Monthly_Data` | Monthly price observations for precious and selected industrial metals |
| `Quarterly_QoQ` | Quarterly average prices and quarter-over-quarter changes |
| `Annual_CV` | Annual average prices, December averages, annual CV and annual changes |
| `Metal_Summary` | Cross-period summary metrics |
| `Return_Correlations` | Pearson correlations of monthly percentage returns |
| `Macro_Series` | Candidate official CPI/PPI indicators and source references; raw macro observations are not loaded |
| `Industry_Cost_Paths` | Conceptual input-cost transmission paths and limitations |
| `Methodology` | Source definitions and calculation notes |

## Key methodological choices

- Monthly averages are used rather than daily prices or month-end closes.
- Quarterly QoQ change is calculated from quarterly average prices:  
  `(current-quarter average / previous-quarter average - 1) × 100`.
- Price-level CV is the sample standard deviation of monthly price levels divided by their mean.
- Return correlations use monthly percentage returns and describe co-movement, not causation.
- Gold, silver, platinum and the base-metal comparators are based on the supplied World Bank commodity workbook. Palladium is a separately sourced IMF Primary Commodity Prices (PCPS) series; see [methodology](docs/METHODOLOGY.md).

## Important data-quality and interpretation notes

1. **CPI/PPI comparison is not yet calculated.** The workbook lists candidate official indicators for the United States, euro area, China, Japan and India, but the underlying monthly index observations were not loaded. Therefore, no metal-versus-inflation correlation or regression is claimed.
2. **Industrial cost pathways are qualitative.** Jewelry fabrication, electronic components and catalytic materials have different input mixes, labor costs, energy exposure and supply chains. The project does not claim a universal global processing-cost index or estimate pass-through coefficients.
3. **Palladium uses a separate source.** Its series should not be assumed to be perfectly identical in construction or publication conventions to the World Bank series.
4. **Audit note on the summary volatility fields:** in the current workbook/dashboard build, the monthly-return standard deviation and best/worst monthly return fields are stored as decimal returns while their displayed headers imply percentages. Those specific fields should be multiplied by 100 before percentage interpretation. The price-level CV fields are already expressed in percent. Correlation values are unaffected. Recompute from `Monthly_Data` before using those return-volatility summary figures in downstream analysis.
5. Values are nominal USD and are not inflation-adjusted.

## Reproducibility

The Excel workbook contains the prepared observations and derived tables. The dashboard is a self-contained HTML document apart from its Plotly JavaScript dependency, which is loaded from a CDN; an internet connection is required for chart rendering.

## Sources

- [World Bank – Commodity Markets](https://www.worldbank.org/en/research/commodity-markets)
- [World Bank – Pink Sheet data and documentation](https://www.worldbank.org/en/research/commodity-markets)
- [IMF Primary Commodity Prices (PCPS)](https://www.imf.org/en/Research/commodity-prices)
- [OECD – Consumer price indices](https://www.oecd.org/en/data/indicators/inflation-cpi.html)
- [U.S. Bureau of Labor Statistics – Producer Price Index](https://www.bls.gov/ppi/)

## License

Released under the MIT License. See [LICENSE](LICENSE).

---

**Author:** [sinanaghdi](https://github.com/sinanaghdi)
