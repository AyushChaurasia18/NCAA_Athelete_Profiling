ML_2025_Project9_Group10: Ensemble Learning-Based Optimal Line-Up Prediction for Basketball

🌟 Project Overview

This repository contains the complete work for our project, "Ensemble Learning-Based Optimal Line-Up Prediction for Basketball." The primary goal was to develop a comprehensive, explainable framework to profile NCAA basketball athletes and predict the optimal five-player line-up for maximizing win probability.

We leveraged game data from the Northeast Conference (NEC) and Metro Atlantic Athletic Conference (MAAC) from the 2020-2024 seasons.

Our methodology involved a two-stage process:

Player Profiling (Clustering): We used advanced clustering algorithms to move beyond traditional, rigid player positions (e.g., 'PG', 'SF') and identify "soft" or "fluid" player profiles based on their performance metrics.

Win Prediction (Classification): We used an ensemble machine learning model to predict game outcomes based on a team's line-up, which then serves as the engine for finding the "optimal" line-up.

🛠️ Technical Architecture & Methodology

Stage 1: Player Profiling with Fuzzy & Spectral Clustering

Traditional basketball positions are outdated. Our first step was to discover data-driven player profiles.

Fuzzy C-means (FCM) Clustering:

Purpose: To create "soft" player profiles. Instead of assigning a player to one position, FCM assigns a membership score (probability) to each of the 5 positions (PG, SG, SF, PF, C).

Result: This model produced the ncaa_with_soft_positions.csv file, where each player has a fluid profile (e.g., 60% SF, 30% PF, 10% C) that better captures their on-court role.

Spectral Clustering with Feature Selection (SC-FS):

Purpose: To identify the most relevant combination of performance stats (e.g., PTS, AST, REB) for grouping players.

Result: We ran experiments on all feature subsets to find the combination that produced the most meaningful and distinct clusters, with results logged in all_subsets_spectralclustering.txt.

Stage 2: Win Prediction with Ensemble Learning

With player profiles established, we built a model to predict wins.

Ensemble Classification Model (Random Forest):

Purpose: To predict the outcome of a game (Win/Loss) based on the aggregate statistics of a team's five-player line-up.

Result: This predictive model acts as our core engine. By feeding it different combinations of players (based on their "soft" profiles), we can simulate and identify the specific line-up that yields the highest win probability.

👤 My Individual Contributions

As a key member of this project, I was directly involved in model implementation, data validation, and technical reporting.

Category

Contribution Details

Win Prediction Model

Contributed to the development and tuning of the ensemble classification model (Random Forest), which serves as the core engine for predicting game outcomes and identifying optimal line-ups.

Player Profiling (FCM)

Helped implement the Fuzzy C-means (FCM) clustering algorithm to generate the "soft position" profiles for each athlete, which are a core innovation of this project (see ncaa_with_soft_positions.csv).

Code Debugging & Validation

Responsible for debugging the data processing pipelines and validating the outputs of the clustering and classification models to ensure numerical stability and accuracy.

Reporting & Analysis

Co-authored and finalized the Endsem_Report.pdf, synthesizing the complex clustering and classification results into a single, cohesive technical document that explains our methodology and findings.

📁 Repository Contents

Endsem_Report.pdf: The final project report detailing the complete methodology, results, and analysis.

Midsem_Report.pdf: The mid-term progress report outlining initial clustering experiments.

code/:  Contains the Python scripts and Jupyter notebooks used for:

Data Preprocessing

Fuzzy C-means (FCM) Implementation

Spectral Clustering & Feature Selection

Ensemble Model (Random Forest) Training

data/:

players_with_positions.csv: The raw input dataset with hard-coded traditional player positions.

ncaa_with_soft_positions.csv: The output file from our FCM model, showing the soft membership probabilities for each player.

all_subsets_spectralclustering.txt: A log file from our feature selection experiments for Spectral Clustering, showing the performance of different statistical combinations.
