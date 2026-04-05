# Does VAR Lead to More Red Cards?

## Overview
An econometric analysis investigating whether the introduction of the Video Assistant Referee (VAR) causally increases the number of red cards awarded per match in 3 top tier leagues in European football. 

Using match-level data from 11,475 games across the Bundesliga, Ligue 1, and Premier League (2014–2025), this project exploits uses the staggered adoption of VAR as a natural experiment using a Two-Way Fixed Effects (TWFE) Difference-in-Differences (DiD) design.

## Dataset
Match-level data for all league matches across the Bundesliga, Ligue 1, and Premier League from 2014 to 2025, yielding 11,475 observations.
Source: https://github.com/Shehrhass/Causal-Analysis/main/MasterData_14_to_25.csv
Source: Match-level data is from football-data.co.uk, covering the top-tier leagues of Germany, France, and England over a 10-year panel.


## ✨ Features
* **Staggered Difference-in-Differences (DiD):** Estimates the causal effect of VAR adoption using home-away team and season fixed effects.
* **Event Study Analysis:** Visualizes pre-treatment and post-treatment trends to validate the parallel-trends assumption.
* **Heterogeneity Testing:** Breaks down the VAR effect by individual league to analyze the impact of league-specific refereeing cultures.
* **Robustness Checks:** Includes Poisson Maximum Likelihood Estimation (MLE) to account for the zero-inflated, count nature of red card data, alongside narrow-window regressions.

## How to Run
1. Clone this repository
2. Install dependencies: `pip install -r requirements.txt`
3. Open `ShehryarHassan_VAR_redcards_analysis.ipynb` in Jupyter
4. Update the file path in Part 2 Cell 2 to point to your local dataset
5. Run all cells top to bottom

## Results
| Model                 | βVAR  | SE    | p-value | N      | Controls | FE  |
| :---                  | :---  | :---  | :---    | :---   | :---     | :---|
| TWFE - VAR only       | 0.008 | 0.025 | 0.735   | 11,475 | No       | Yes |
| TWFE - VAR + controls | 0.014 | 0.024 | 0.543   | 11,475 | Yes      | Yes |
| +/- 3-season window   | 0.014 | 0.024 | 0.578   | 7,360  | Yes      | Yes |
| Poisson MLE           | 0.088 | 0.139 | 0.527   | 11,475 | Yes      | Yes |
