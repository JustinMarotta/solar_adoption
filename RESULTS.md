# Results

## Research Question

Which structural and socioeconomic factors explain variation in residential solar adoption, conditional on sufficient solar resource and mature technology?

This framing treats solar resource as sufficient so the analysis can focus on barriers and enablers such as capital, housing constraints, policy environment, and equity-related factors.

## How to Review / Reproduce

- Setup and notebook execution order are in [README.md](README.md).
- Modeling details and interpretation are in [03_modeling.ipynb](03_modeling.ipynb).
- Primary outputs are in [model_results/model_summary.csv](model_results/model_summary.csv) and [model_results/model_coefficients.csv](model_results/model_coefficients.csv).

## Key Findings

### Solar Adoption Enablers

1. **Income**
   - Median household income is the strongest positive predictor of solar adoption in the model.  
   - Higher-income counties tend to adopt more solar, as expected: solar installations require significant upfront capital.  

2. **Education**
   - Counties with a higher proportion of residents holding a bachelor's degree or higher show increased adoption.  
   - Likely reflects greater awareness, understanding, and access to information about solar technology and incentives.  

3. **Policy Incentive Programs**
   - A greater number of local solar incentive programs is associated with higher adoption.  
   - Financial support reduces upfront cost barriers and encourages households to invest in solar.  

4. **Housing Type**
   - Counties with more single-family homes have higher adoption.  
   - Structural feasibility matters: rooftop solar is easier to install on single-family homes than on apartments or condos.

---

### Solar Adoption Barriers

1. **Systemic Barriers**
   - Counties with higher proportions of Black and Hispanic residents tend to have lower solar adoption.  
   - This is **not causal**. Likely confounded by structural inequities, such as: 
     - Wealth gaps → less capital for upfront costs  
     - Discriminatory lending → harder access to solar financing  
     - Geographic clustering in areas with fewer incentive programs  

2. **Urban Areas**
   - Compared to the reference category "Rural areas," both urban and suburban counties show reduced solar adoption.  
   - Possible explanations:
     - Higher proportion of renters → less ability to install solar  
     - Apartments/condos → structural barriers for rooftop solar  
     - Rural areas, in contrast, often have:
       - More single-family homes → easier installations  
       - Higher electricity costs → stronger financial incentive  
       - Agricultural areas → more roof/land space  

3. **Homeownership Rate**
   - Unexpectedly, higher homeownership rates are associated with lower solar adoption in the model.  
   - Possible explanations:
     - Multicollinearity: highly correlated with other variables    
     - Interaction effects: homeownership may influence adoption differently in different contexts


## Part B: Evaluating Implications on Business Value

The county-level analysis of residential solar adoption identifies structural barriers and enablers that have direct implications for business value, particularly for companies involved in solar deployment, financing, and policy consulting.

---

### 1. Income and Financing Access

- **Insight:** Higher median household income strongly predicts adoption.  
- **Business implications:**  
  - Companies can target financing products or solar offerings to lower-income counties with untapped potential.  
  - Reducing upfront cost barriers expands the addressable market.  
- **Strategic value:** 
  - Generates incremental revenue: More installations translate directly into sales, service, and financing income.
  - Long-term strategic advantage: Establishes presence in emerging markets, potentially locking in future growth.
- **Policy** Low-interest loans, targeted rebates, community solar for lower-income households. 
- **Downsides** Budget limits (subsidies & rebates require public funding), risk of regressive benefits (may inadvertently benefit wealthier households), admin complexity.
- **Economics** Cost per additional installation, ROI of financing programs
- **Metrics to quantify impact:** Adoption rate increase in low/moderate income areas, reduction in income adoption gap, incremental revenue from programs

---

### 2. Education and Awareness

- **Insight:** Higher educational attainment is associated with higher adoption.  
- **Business implications:**  
  - Solar companies can invest in awareness campaigns to increase adoption where education/awareness is lower.  
  - Educational outreach reduces customer acquisition friction.  
- **Strategic value:** Accelerates adoption, improves conversion rates, and enhances brand positioning as a trusted energy partner.  
- **Policy** Outreach campaigns, workshops, school/community programs.
- **Downsides** Program costs, delayed effects.
- **Economics** Customer acquisition cost vs adoption increase
- **Metrics:** Adoption growth after campaigns, survey-based awareness improvements, lead conversion rates.

---

### 3. Policy Incentive Programs

- **Insight:** Presence of net metering, rebates, or tax credits correlates with higher adoption.  
- **Business implications:**  
  - Solar providers can prioritize markets with strong policy support to maximize early adoption.  
  - Policymakers or utilities can design incentives that reduce financial barriers and expand market size.  
- **Strategic value:** Incentives directly influence ROI and market viability, guiding investment decisions. 
- **Policy** Relies on public policy
- **Downsides** Relies on public policies out of company control, difficult to influence & grow.
- **Economics** $ spent per kW installed, ROI of incentive programs.
- **Metrics:** Adoption rate increase in counties with new incentives, uptake relative to program cost.

---

### 4. Housing Type and Urbanicity

- **Insight:** Single-family homes and rural counties adopt more, urban/multi-family dwellings less.  
- **Business implications:**  
  - For companies: focus installation and financing strategies on structurally feasible segments or develop community/shared solar solutions for multi-family units.  
  - Work with policy makers to update zoning, permitting, and building code adjustments to unlock new markets.  
- **Strategic value:** Expands addressable customer base while managing deployment costs.  
- **Policy** Community/shared solar for multi-family; rooftop incentives, supportive codes.
- **Downsides** Admin overhead, higher cost per household.
- **Economics** Cost per household served, potential energy generated.
- **Metrics:** Incremental installations in target housing types, cost per installation, adoption rate improvements in urban or multi-family areas.

---

### 5. Equity and Structural Barriers

- **Insight:** Counties with higher Black and Hispanic populations show lower adoption, reflecting structural inequities.  
- **Business implications:**  
  - Targeted programs can expand adoption in underserved communities, increasing market share and social impact.  
  - Aligns with ESG (Environmental, Social, Governance) and corporate responsibility objectives.  
- **Strategic value:** Enhances market diversification, brand reputation, and compliance with equity-focused mandates.  
- **Policy**: Targeted incentives, outreach, financing support in underserved communities.
- **Downsides**: Requires careful design to avoid inefficiency or stigmatization.
- **Economics**: Higher upfront costs per household; long-term social impact benefits (reduce adoption gaps, increases overall market size).
- **Metrics:** Reduction in adoption gaps, uptake among minoritized households, incremental revenue from previously untapped segments.

---

**Summary:**  
By linking structural barriers and enablers to actionable strategies, businesses can use these insights to **increase adoption, optimize marketing and deployment, improve ROI, and advance equity goals**, all of which contribute to measurable business value.