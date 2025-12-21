# Solar Adoption Analysis

Research Question: What factors are associated with under-adoption of solar energy, indicating structural barriers?

## Project Overview

Analysis of solar adoption patterns across US counties using:
1. **Outcome**: LBNL Tracking the Sun - Solar installations by county
2. **Control**: NLDAS - Sunlight Data
3. **Barriers**: US Census/ACS - Demographics (income, homeownership, urbanicity)
4. **Policy**: DSIRE - Net metering policy indicators

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
