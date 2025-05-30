# Nomao Dataset Deduplication

## Overview
This project aims to predict whether two records refer to the same place using the Nomao dataset. By analyzing various attributes, we identify key features that influence the deduplication decision.

## Dataset
- **Source:** [UCI Machine Learning Repository - Nomao Dataset](https://archive.ics.uci.edu/dataset/227/nomao)
- **Attributes:** 120 features including names, phone numbers, and locations.
- **Target Variable:** `label` indicating if two records refer to the same place.

## Project Structure
- `data/`: Contains the dataset files.
- `notebooks/`: Jupyter notebooks for data analysis and modeling.
- `README.md`: Project documentation.
- `requirements.txt`: List of required Python packages.

## How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/nomao-deduplication.git
   cd nomao-deduplication
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Launch Jupyter Notebook:
   ```bash
   jupyter notebook notebooks/nomao_deduplication.ipynb
   ```

## Results
- Achieved high classification performance with Random Forest Classifier.
- Identified top features influencing deduplication decisions.

## Future Work
- Explore advanced models like XGBoost.
- Implement active learning strategies for improved performance.
