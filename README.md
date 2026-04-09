# Do Local Industrial Policies Drive Battery Energy Storage Innovation?
This repository provides the BESS policy text processing code, panel data, and Stata code used in the paper Do Local Industrial Policies Drive Battery Energy Storage Innovation? Evidence of Threshold Effects and Industrial-Chain Spillovers from China.

# Research Overview
This study examines the impact of local industrial policies on BESS innovation in China using a panel dataset of 296 cities over the period 2008–2020. We develop a staggered Difference-in-Differences (DID) framework to identify the causal effects of local BESS policy interventions under staggered policy adoption. To better capture policy heterogeneity, we employ Large Language Models (LLMs) to construct continuous measures of policy intensity from large-scale policy documents, and we match these measures to granted BESS invention patents identified through a dual-track keyword and International Patent Classification (IPC) retrieval strategy. This framework enables us to move beyond binary policy treatments and aggregate innovation proxies, and instead examine the scale, direction, and vertical distribution of innovation responses within the BESS industry.

The results show that local industrial policies significantly promote directed innovation in BESS, increasing core technological breakthroughs by 12.4% without stimulating generic patent expansion. We further identify a pronounced nonlinear threshold effect. At low levels of policy intensity, the estimated effects are negative, suggesting possible compliance frictions and short-term crowding-out, but these effects are not statistically significant. Once policy support accumulates beyond a critical threshold, however, the marginal effects turn significantly positive, with elasticities of 25.7% and 29.3% for policy quantity and policy quality, respectively. We also find strong industrial-chain spillovers: stringent downstream policies generate demand-pull pressures that induce a 28.5% increase in upstream core electrochemistry innovation. Overall, our findings show that local industrial policies can shape not only the scale but also the direction and structure of BESS innovation, offering evidence for more targeted and effective policy design in support of the energy transition.

# File Name	Description
Baseline Staggered DID.do：Stata do-file for baseline staggered difference-in-differences (DID) estimation, including core regression specifications, parallel trend tests, and robustness checks.

CSDID.do：Stata do-file for Callaway-Sant'Anna DID (CSDID) estimation, a robust method for staggered treatment adoption with heterogeneous treatment effects.
Industry Chain Spillovers.do：Stata do-file for industry chain spillover effect analysis, examining how policy shocks propagate across upstream/midstram/downstream industries, etc.

Regional Heterogeneity.do：Stata do-file for regional heterogeneity analysis, testing differential policy effects across geographic regions.

llm_api.py：Python script for LLM API integration and prompt engineering. Handles API calls to large language models, constructs standardized prompts for policy analysis, and manages request/response workflows.

process_policies.py：Python script for structured extraction of LLM analysis results. Parses unstructured LLM outputs, standardizes policy coding, and transforms raw model responses into machine-readable, analysis-ready structured data.

panel_data.xlsx：Raw panel dataset used for all regression analyses, containing city-level variables, treatment timing, and control variables.

README.md	Project documentation file (this file).

# Data availability
BESS policy data are obtained from the Pkulaw Law Database (https://www.pkulaw.com/). BESS patent data are sourced from the Innojoy Patent Database (https://www.innojoy.com/). Control variables are collected from the China City Statistical Yearbook.

# Usage Instructions
Policy Data Preparation: 
Use llm_api.py to send policy text to the LLM API with pre-built prompts.

Use process_policies.py to extract and structure the LLM's output into a format compatible with the panel dataset.

# Dependencies
Stata:
Required packages: csdid, reghdfe, estout (install via ssc install if missing)
Stata version 16 or higher recommended

Python:
Required libraries: openai (or other LLM API clients), pandas, numpy, json, re
Python version 3.8 or higher recommended

# Notes
All regression code is pre-configured for the panel_data.xlsx dataset. Modify file paths and variable names as needed for your specific analysis.

Ensure API keys are securely stored and not hard-coded in llm_api.py for production use.

For reproducibility, all do-files and Python scripts include detailed comments for each step of the analysis.

# Contact
For questions or issues related to the code or analysis, please contact the repository maintainer.
