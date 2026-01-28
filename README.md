This project presents a two-stage machine learning framework for predicting video game reception by modeling pre-release expectations and post-release player experience separately. The study predicts critic ratings and user ratings using structured metadata, engineered features, and execution-level in-game attributes.

The project is accompanied by a research paper that analyzes feature importance, model behavior, and the limits of prediction at different stages of the game lifecycle.

Project Overview

Video game reception evolves across time. Before release, ratings are shaped by expectations, brand reputation, and perceived value. After release, reception is driven primarily by gameplay experience, replayability, and execution quality.

To capture this distinction, the project implements two independent models:
	•	Model 1 (Pre-release):
Predicts expected ratings using only features available before launch.
	•	Model 2 (Post-release):
Predicts realized ratings using execution-level in-game features.

Critic and user ratings are modeled separately in both stages.

Dataset

The dataset was manually curated from publicly available sources and engineered for interpretability and temporal validity.

Data Sources
	•	IGDB
	•	HowLongToBeat
	•	IGN
	•	Steam
	•	Metacritic
	•	IMDb

Dataset Structure
	•	Raw dataset: Manually curated game metadata
	•	Engineered dataset: Feature-engineered version used for modeling

The final pre-release dataset contains 170 games, which is the dataset used for all reported Model 1 results in the paper.

Feature Engineering

Key feature categories include:

Pre-release Features
	•	Structural metadata (genre, platforms, modes)
	•	Pricing and playtime-based value metrics
	•	Binary indicators (open-world, sequel, modding support)
	•	Studio and franchise historical average ratings
	•	Unique factor indicator for non-standard gameplay experiences

Post-release Features
	•	Story depth
	•	Gameplay quality
	•	Replayability
	•	World immersion
	•	Narrative and audio quality indicators

Derived features such as price per story hour and content density were used to capture perceived value and game design balance.

Models Used

The following ensemble regression models were evaluated:
	•	Random Forest Regressor (primary model)
	•	Gradient Boosting Regressor
	•	XGBoost Regressor

Random Forest was selected as the primary model due to its robustness and interpretability.

Evaluation Metrics

Model performance was evaluated using:
	•	Mean Absolute Error (MAE)
	•	Root Mean Squared Error (RMSE)
	•	R² score

All evaluations were conducted separately for critic and user ratings.

Results Summary
	•	Pre-release prediction shows moderate predictability, driven mainly by studio reputation, pricing, and modding support.
	•	Post-release prediction achieves substantially higher performance, dominated by gameplay quality and replayability.
	•	Critic ratings are consistently more predictable than user ratings.
	•	Replayability is the most influential post-release feature across models.

Detailed results and feature importance analysis are presented in the accompanying paper.

Repository Structure
game-rating-prediction/
│
├── data/
│   ├── Games List 170.csv
│   ├── In Game Features.csv
│   └── games_engineered.csv
│
├── notebooks/
│   ├── game_rating_prediction_pre_release.ipynb
│   ├── game_rating_prediction_post_release.ipynb
│
├── results/
│   └── metrics_summary.txt
│
├── README.md
└── requirements.txt

Paper

A research paper based on this project is currently in preparation, presenting the methodology, results, discussion, and future work in conference format.

Notes
	•	This repository is intended as a research artifact supporting the paper.
	•	The project emphasizes interpretability and lifecycle-aware modeling rather than commercial prediction.
	•	Large language models were used only for limited assistance in feature standardization, with all outputs manually reviewed.

Author

Paritosh Vishwasrao

