# CCDATSCL_COM221_PROJECT

Final project repository for a data science course. This project focuses on data ingestion, preprocessing, exploratory analysis, and summarizing findings from weekly datasets.

## Project Name/Intro
This repository contains the final data science project work for the course. It consolidates multiple weekly datasets into a combined dataset and analyzes patterns using Jupyter notebooks.

## Core Technical Concepts/Inspiration
The project demonstrates practical data science workflow steps: data cleaning, feature engineering, exploratory data analysis, and high-level interpretation of results for a course final.

## Getting Started/Requirements/Prerequisites/Dependencies
1. Create and activate a Python environment (Python 3.8+ recommended).
2. Install dependencies:
   - `pip install jupyter pandas numpy matplotlib seaborn scikit-learn`
3. Start Jupyter:
   - `jupyter notebook`
4. Open the notebooks listed below to reproduce the preprocessing and analysis steps.

## Data
- `Datasets/Week_*/week_*.csv` contain the weekly source data files.
- `combined_player_data.csv` is the consolidated dataset produced during preprocessing.

## Project Structure
- `DataSci_Preprocessing.ipynb` performs data cleaning and merges weekly data.
- `Datasci_Analysis.ipynb` performs exploratory analysis and summarizes findings.
- `Datasets/` contains the raw weekly CSV files.

## Results/Deliverables
The notebooks document the end-to-end workflow and capture the final analysis for the course project.

## Contributing
This repository is a course final project and is not accepting external contributions.

## Credits
- Repository owner: rbodarve.
- README template based on Zalando's README Template (via https://github.com/zalando/zalando-howto-open-source and https://github.com/matiassingers/awesome-readme).

## License
No license specified.

## Environment note
The notebooks were run under WSL (Ubuntu) on Windows. Saved outputs therefore show Linux paths such as `/home/rbo/...`. The outputs are kept as submitted.

## Review notes (2026-10-17)
1. Run order: run `DataSci_Preprocessing.ipynb` first. It writes `combined_player_data.csv`. Then run `Datasci_Analysis.ipynb`. Start Jupyter from the repo root.
2. Preprocessing calls the OpenDota API (heroes, items), so it needs internet. The committed CSV lets you skip it.
3. Data: one player's 99 matches over 12 weekly files. The results describe that player, not Dota players in general.
4. Limitation: "weekly" in the analysis means calendar weeks (Mon–Sun) from `start_time`. This gives 13 buckets, and two of them hold only 1 and 3 matches. Weekly trends and CV are noisy.
5. Limitation: the hero win-rate and hero KDA rankings rest on very few games. 28 of 37 heroes have 3 games or fewer, and 18 have only 1 game. 25 heroes show a win rate of exactly 0 % or 100 %. Treat the top/bottom-10 charts as descriptive only.
6. Limitation: the win-vs-loss tests compare metrics that the outcome itself drives. They show association, not cause.
7. KDA in the analysis = (kills + assists) / max(deaths, 1). It differs from the dataset's own `kda` column.
8. The row order of the regenerated CSV can differ by OS. The content is the same.
