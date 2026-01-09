# Solar Adoption Analysis

## Quick Start

Analysis of structural barriers to residential solar adoption across U.S. counties using machine learning.

```bash
# Clone and setup
git clone https://github.com/JustinMarotta/solar_adoption.git
cd solar_adoption

# Create virtual environment with Python 3.12.12
pyenv virtualenv 3.12.12 solar-env
pyenv activate solar-env

# Install dependencies
pip install -r requirements.txt

# Set up API keys (required for data collection)
echo "HUD_API_TOKEN=your_token_here" > .env
echo "CENSUS_API_KEY=your_key_here" >> .env

# Run notebooks in order
# 01_data_preparation.ipynb → 02_EDA.ipynb → 03_modeling.ipynb
```

### Start here (for reviewers)

- Read [RESULTS.md](RESULTS.md) for key findings and business implications.
- Use these direct links to jump to the relevant sections in Notebooks:
   - Data prep + assumptions: [01_data_preparation.ipynb](01_data_preparation.ipynb#methodological-assumptions-consequences)
   - EDA + decisions: [02_EDA.ipynb](02_EDA.ipynb#key-decisions)
   - Modeling approach + results: [03_modeling.ipynb](03_modeling.ipynb#modeling-approach-justification)
- To reproduce the dataset build and analysis, run notebooks in order: [01_data_preparation.ipynb](01_data_preparation.ipynb) → [02_EDA.ipynb](02_EDA.ipynb) → [03_modeling.ipynb](03_modeling.ipynb).
- Model artifacts are saved in [model_results/](model_results/).

[Results](RESULTS.md) | [Full setup instructions](#environment-setup) | [Data sources](#data-sources) | [Project structure](#project-structure)

---

## Table of Contents

- [Start Here](#start-here-for-reviewers)
- [Results](RESULTS.md)
- [Research Question](#research-question)
- [Project Overview](#project-overview)
  - [Scope](#scope)
- [Environment Setup](#environment-setup)
  - [Prerequisites](#prerequisites)
  - [Installation Steps](#installation-steps)
  - [Running the Notebooks](#running-the-notebooks)
- [Project Structure](#project-structure)
- [Data Sources](#data-sources)
- [Future Improvements](#future-improvements)

---

### Research Question

Which structural and socioeconomic factors are associated with under-adoption of residential solar, **conditional on sufficient solar resource and mature technology**?  

Sunlight is excluded from the main analysis because:  
- It explains less than 1% of variance in log-adoption across most counties.  
- Data is available for only ~50% of counties, and imputation could introduce bias.  

Effectively, this treats solar resource as sufficient, allowing the analysis to focus on **capital, housing, policy, and equity-related barriers** that drive under-adoption.

## Project Overview

Analysis of solar adoption patterns across US counties using:
1. **Outcome**: LBNL Tracking the Sun - Solar installations by county
2. **Control**: NLDAS - Sunlight Data
3. **Barriers**: US Census/ACS - Demographics (income, homeownership, urbanicity)
4. **Policy**: DSIRE - Net metering policy indicators

### Features

Affordability/Financing:
- Median household income

Structural Feasibility:
- Homeownership rate
- Single family home %

Demographics:
- % Bachelors or higher education
- % White
- % Black
- % Hispanic
- Avg household size
    
Geography/Physical:
- Population density
- Urbanicity

    
Policy:
- Has_net_metering
- Has_solar_incentive
- Total # of solar programs

Control:
- Average daily sunlight (KJ/m²)

### Scope

**Geographic Focus: United States (County-Level)**

County-level analysis is appropriate because:
- In the U.S., counties (or county-equivalents) are primary legal divisions of states and are widely used as standard reporting geographies by the U.S. Census Bureau for demographic and socioeconomic data, making them a practical unit for comparative analysis¹
- Sufficient variation in adoption rates, demographics, and policy environments across ~3,100 counties
- Balances granularity with data availability (ZIP-level would have excessive missing data; state-level would lose important within-state variation)

**Technology Focus: Residential Solar**

Residential adoption matters because:
- **Scale**: The residential segment represents one of the largest opportunities for distributed solar growth, spanning millions of single-family homes nationwide. NREL estimates U.S. rooftop solar technical potential at approximately 1,118 GW.²
- **Decentralization**: Rooftop solar supports grid resilience, reduces transmission losses (commonly estimated at 5–10% in distribution systems), and supports more decentralized energy production³
- **Business relevance**: Understanding residential adoption barriers informs market targeting, financing strategies, and policy advocacy for solar companies, supporting scalable customer acquisition and product design.⁴
- **Equity implications**: Residential adoption gaps highlight structural inequities in clean energy access. Research shows substantially lower rooftop solar adoption in low-income and majority-minority communities, even after accounting for income and homeownership.⁵

---

**References:**
1. U.S. Census Bureau. "County-Level Data Products." https://www.census.gov/programs-surveys/acs/geography-acs/geography-boundaries-by-year.html
2. National Renewable Energy Laboratory (NREL). Rooftop Solar Photovoltaic Technical Potential in the United States. https://docs.nrel.gov/docs/fy16osti/65298.pdf
3. Global Solar Council. Solar Energy and Its Benefits for the Power Grid. https://www.globalsolarcouncil.org/news/solar-energy-and-its-countless-benefits-for-the-power-grid/
4. Solar Energy Industries Association (SEIA) & Wood Mackenzie. U.S. Solar Market Insight Report (2024). https://seia.org/research-resources/solar-market-insight-report-q4-2025/
5. O'Shaughnessy, E., Heeter, J., & Graziano, M. (2021). "Disparities in rooftop photovoltaic adoption by income in the United States." *Nature Energy*, 6(12), 1124-1130. https://escholarship.org/uc/item/5sz1j52z
   

## Environment Setup

### Prerequisites
- Python 3.12.12
- pip (Python package manager)
- Git

### Installation Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/JustinMarotta/solar_adoption.git
   cd solar_adoption
   ```

2. **Create a virtual environment with pyenv**
   ```bash
   # Create virtual environment with Python 3.12.12
   pyenv virtualenv 3.12.12 solar-env
   
   # Activate the virtual environment
   pyenv activate solar-env
   
   # (Optional) Set as local environment for this directory
   pyenv local solar-env
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up environment variables** (if needed)
   
   Create a `.env` file in the project root directory if you need to configure any API keys or credentials:
   ```bash
   touch .env
   ```
   
   Add any required environment variables to the `.env` file.

   Required API Keys:
   - HUD_API_TOKEN (https://www.huduser.gov/portal/dataset/uspszip-api.html)
   - CENSUS_API_KEY (https://api.census.gov/data/key_signup.html)

### Running the Notebooks

1. **Start Jupyter**
   
   The project uses Jupyter notebooks. You can run them using VS Code with the Jupyter extension, or launch Jupyter in your browser:
   ```bash
   jupyter notebook
   ```

2. **Execute notebooks in order**
   - `01_data_preparation.ipynb` - Data collection and preprocessing
   - `02_EDA.ipynb` - Exploratory data analysis
   - `03_modeling.ipynb` - Statistical modeling and analysis

### Project Structure

```
solar_adoption/
├── 01_data_preparation.ipynb    # Data collection and preprocessing
├── 02_EDA.ipynb                 # Exploratory data analysis
├── 03_modeling.ipynb            # Statistical modeling
├── README.md                     # This file
├── RESULTS.md                    # Key findings and business implications
├── requirements.txt              # Python dependencies
├── model_results/               # Model outputs
│   ├── model_coefficients.csv
│   └── model_summary.csv
├── modeling_data/               # Processed datasets
│   └── merged_solar_dataset.csv
└── source_datasets/             # Raw data files
    ├── dsire-2025-11/          # DSIRE policy data
    └── LBNL_TrackingTheSun2025_PublicDataFile/ # Tracking the sun data
```

### Data Sources

- **LBNL Tracking the Sun**: Solar installation data
    - Download from https://emp.lbl.gov/tracking-the-sun
    - Link ZIP to County level via https://www.huduser.gov/portal/datasets/usps_crosswalk.html (Access via API) 
- **NLDAS Sunlight Data**: County-Level Average Daily Sunlight Data derived from NLDAS
    -Access data via API: https://www.arcgis.com/home/item.html?id=8a193dda032d48e884b7be3ecea7189c
- **US Census/ACS**: Demographic and socioeconomic data
    - Access via API: https://www.census.gov/data/developers/data-sets/acs-5year.html
- **DSIRE**: Database of State Incentives for Renewables & Efficiency
    - Data download: https://www.dsireusa.org/resources/database-archives/


### Future Improvements

**Data Coverage & Quality**
- Expand geographic coverage: Current LBNL Tracking the Sun data is missing nearly half of U.S. states; improved coverage would enhance model generalizability and allow nationwide barrier analysis
- Incorporate temporal dynamics: Current analysis uses cumulative 2024 adoption; time-series analysis could reveal how barriers change over policy implementation periods
- Reduce missing data: Sunlight data only available for ~50% of counties; alternative solar resource datasets (NREL PVWatts) could improve coverage

**Model Development**
- Improve explanatory power: Current model R² indicates significant unexplained variance; candidate features include:
  - Electricity prices (higher utility costs → stronger financial incentive)
  - Historical electricity generation mix (fossil-heavy states may have cultural barriers)
  - Local installer density (market maturity proxy)
  - Credit score distributions (financing access proxy)
- Test non-linear models: Elastic Net assumes linear relationships; tree-based models (Random Forest, Gradient Boosting) could capture interaction effects and thresholds
- Interaction terms: Test income × policy interactions (do incentives matter more in low-income areas?) and housing × urbanicity (multi-family barriers in cities)

**Policy Analysis**
- Comparative case studies: Deep-dive analysis of high-adoption states (California, Vermont, Massachusetts) vs. low-adoption states (New York, Illinois, Alabama)
  - What specific policies (net metering rates, tax credits, permitting requirements) differentiate leaders from laggards?
  - Are there replicable policy packages that could be exported to low-adoption states?
- Policy discontinuity designs: Leverage abrupt policy changes (e.g., California NEM 3.0 solar policy transition) to estimate causal effects of specific incentives

**Equity Analysis**
- Disaggregate racial/ethnic effects: Current model shows negative coefficients for Black and Hispanic populations; further analysis needed to disentangle:
  - Direct wealth/financing barriers vs. geographic clustering in low-incentive areas
  - Discriminatory lending practices vs. targeted marketing gaps
- Community solar analysis: Evaluate whether shared solar programs reduce adoption gaps for renters and multi-family households
