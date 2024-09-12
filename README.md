# Netflix Recommendation System

## Overview

This project implements a Netflix recommendation system using a content-based approach. It leverages the TF-IDF (Term Frequency-Inverse Document Frequency) vectorizer to compute similarity scores between movies based on their descriptions, cast, and director. The system provides movie recommendations based on a given title from the dataset.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Data](#data)
- [Visualization](#visualization)
- [Recommendation System](#recommendation-system)
- [License](#license)

## Installation

To run this project, you'll need Python and several libraries. You can install the necessary libraries using `pip`. 

1. Clone the repository:
    ```bash
    git clone https://github.com/brijendras007/netflix-recommendation-system.git
    cd netflix-recommendation-system
    ```

2. Install the required libraries:
    ```bash
    pip install numpy pandas seaborn matplotlib missingno scikit-learn plotly autoviz
    ```

## Usage

1. Place your dataset (`netflix_titles.csv`) in the project directory or update the file path in the script.

2. Run the script:
    ```bash
    python netflix_recommendation_system.py
    ```

3. The script will print recommendations for sample titles and display visualizations.

## Data

The dataset used in this project is `netflix_titles.csv`, which contains the following columns:
- `title`: Title of the movie or show.
- `description`: Brief description of the movie or show.
- `cast`: Main cast of the movie or show.
- `director`: Director of the movie or show.
- `country`: Country where the movie or show was produced.
- `rating`: Rating of the movie or show.

The dataset can be found at [Netflix Dataset](https://www.kaggle.com/datasets).

## Visualization

The project includes visualizations to understand the data better:
- **Missing Values Heatmap:** Displays missing values in the dataset.
- **Top 15 Countries:** Bar chart showing the top 15 countries with the most Netflix titles.

## Recommendation System

The recommendation system uses a content-based approach with the following steps:

1. **Data Preprocessing:**
    - Handle missing values in `rating`, `cast`, and `country` columns.
    - Combine `description`, `cast`, and `director` into a single text column.

2. **Feature Extraction:**
    - Use TF-IDF Vectorizer to convert text data into numerical features.

3. **Similarity Calculation:**
    - Compute a similarity matrix using a sigmoid kernel.

4. **Recommendation Function:**
    - `recommend(title, sig)`: Given a movie title, this function returns a list of recommended movies based on similarity scores.

### Example

To get recommendations for a movie:

```python
print("Recommendations for 'Kota Factory':")
print(recommend("Kota Factory"))

This will display a list of movies similar to "Kota Factory".
