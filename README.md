# Greggs Growth Intelligence System

## UK Store Network, Socioeconomic Context and Competitive Location Intelligence

This portfolio project develops an end-to-end location-intelligence pipeline for analysing the existing Greggs store network across the United Kingdom.

The project combines OpenStreetMap store-location data with official UK geographic and socioeconomic datasets to examine where Greggs operates, the characteristics of those markets, and the competitive environments surrounding individual stores.

Rather than relying only on city-level comparisons, store coordinates are used to measure the actual proximity and density of selected major competitors within 500 m and 1 km catchments.

For English stores, the spatial features are integrated with the English Indices of Deprivation 2025, population data and rural/urban classifications. Statistical analysis and K-Means clustering are then used to identify recurring store environments and translate them into interpretable strategic market contexts.

> **Independent portfolio project:** This repository is not affiliated with Greggs plc. Strategic contexts describe characteristics of the existing store network and should not be interpreted as confirmed Greggs expansion, sales or profitability recommendations.

## Project Objectives

The analysis addresses five main questions:

1. How is the existing Greggs store network distributed across the UK?
2. What socioeconomic and urban/rural characteristics describe Greggs locations in England?
3. How much selected major-brand competition surrounds individual Greggs stores?
4. How are deprivation, urbanisation and local competition related?
5. Can stores be grouped into meaningful and stable market segments for strategic interpretation?

## Data Sources

- **OpenStreetMap (OSM):** Greggs and selected competitor store locations, coordinates and available location metadata.
- **ONS Postcode Directory — May 2026:** postcode geography, coordinates, LSOA codes and rural/urban classifications.
- **English Indices of Deprivation 2025:** IMD scores, IMD deciles, income, employment and crime measures for English LSOAs.
- **Population estimates:** LSOA-level population values used in the England analytical layer.

## Selected Competitor Brands

The spatial competition analysis includes:

- McDonald's
- Costa Coffee
- Subway
- KFC
- Burger King
- Pret A Manger

These brands represent a selected comparison set rather than the complete UK food-to-go market.

## Analytical Workflow

**Data Collection**  
→ OpenStreetMap extraction of Greggs and competitor locations

**Validation & Cleaning**  
→ removal of non-store OSM objects and review of ambiguous records

**Geographic Enrichment**  
→ postcode matching, spatial recovery of missing postcodes and ONS geography integration

**Socioeconomic Enrichment**  
→ IoD 2025, population and rural/urban features for English stores

**Spatial Competition Engineering**  
→ nearest competitor, competitor counts within 500 m / 1 km, brand diversity and brand-specific proximity features

**Exploratory Data Analysis**  
→ network, deprivation and competition profiling

**Statistical Analysis**  
→ urban/rural comparisons, deprivation–competition associations and group-level testing

**Machine Learning Segmentation**  
→ K-Means clustering, multi-metric cluster selection, profiling and stability testing

**Strategic Interpretation**  
→ market-scale, competitive-pressure and deprivation-context indices, market matrix and strategic action framework

**Reporting Preparation**  
→ final validated Power BI-ready store-level dataset

## Final Analytical Scope

The completed pipeline contains:

- **2,174 cleaned Greggs locations across the UK**
- **7,815 cleaned locations from six selected competitor brands**
- **1,746 English Greggs stores with complete socioeconomic analysis**
- **500 m and 1 km store-level competition features**
- **3 stable K-Means strategic segments**
- **4 strategic market contexts**
- **97 fields in the final Power BI-ready master dataset**
- **13 / 13 final data-quality checks passed**

## Key Findings

- **89.3%** of analysed English Greggs stores are located in urban areas.
- **45.4%** of English analytical stores are located in IMD deciles 1–3.
- The typical UK Greggs location has a selected major competitor very close by; the median nearest-competitor distance is approximately **79 m**.
- The median Greggs location has **3 selected competitors within 1 km**.
- Urban stores are substantially more deprived on average than rural stores and generally face denser local competition.
- Deprivation has only a **weak relationship** with local competition density.
- K-Means identified three stable store-market segments:
  - **Competitive Urban Hubs**
  - **Lower-Competition Local Markets**
  - **High-Deprivation Urban Core**
- The final three-cluster solution achieved a mean Adjusted Rand Index of approximately **0.998** across repeated initialisations.

## Strategic Market Contexts

The project translates market scale and competitive pressure into four descriptive network contexts:

- **Defend & Differentiate**
- **Growth Benchmark Context**
- **Local Coverage**
- **Competitive Exposure**

These categories are descriptive decision-intelligence outputs, not predictions of store profitability.

## Statistical Methods

The statistical analysis includes:

- Welch's independent-samples t-test
- Mann–Whitney U test
- Spearman rank correlation
- Kruskal–Wallis test
- Holm-adjusted pairwise comparisons
- Effect sizes and confidence intervals

## Machine Learning

K-Means clustering is used as an unsupervised segmentation method.

The final segmentation is based on three deliberately distinct dimensions:

- socioeconomic context
- local population scale
- local competitive intensity

Candidate cluster solutions are compared using inertia, silhouette score, Davies–Bouldin index and Calinski–Harabasz score. Cluster stability is then assessed across repeated random initialisations using the Adjusted Rand Index.

## Technology

- Python
- Pandas
- NumPy
- Requests
- SciPy
- Scikit-learn
- Matplotlib
- OpenStreetMap / Overpass API
- ONS data
- Power BI-ready data preparation

## Repository Structure

```text
greggs-growth-intelligence-system/
│
├── notebooks/
│   └── Greggs_Growth_Intelligence_System.ipynb
│
├── data/
│   └── final/
│       └── POWERBI_greggs_growth_intelligence_master.csv
│
├── outputs/
│   ├── figures/
│   └── tables/
│
├── README.md
├── requirements.txt
└── .gitignore
```

Large raw ONS source files are intentionally not stored in the repository. The notebook documents the source datasets and reproducible processing workflow.

## Limitations

- OpenStreetMap is community-maintained and is not an official Greggs or competitor store register.
- The competitor set covers six major brands rather than the entire food-to-go market.
- Socioeconomic analysis is restricted to England because the English Indices of Deprivation are not directly comparable across UK nations.
- No internal Greggs store-level sales, revenue, profitability, rent, footfall or transaction data are used.
- Spatial proximity does not directly measure competitive impact.
- The analysis is primarily cross-sectional rather than longitudinal.

## Next Steps

Possible extensions include:

- completing the interactive Power BI dashboard
- adding additional competitor categories
- using walking/driving travel-time catchments
- analysing historical openings and closures
- integrating real commercial performance measures if reliable data becomes available

## Final Status

**Analytical pipeline: Complete**  
**Final data-quality audit: 13 / 13 PASS**  
**Power BI-ready dataset: Complete**  
**Power BI dashboard: Planned enhancement**
