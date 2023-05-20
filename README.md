# Pokemon Dataset Analysis

This project analyzes a dataset of Pokemon using R programming language. It explores various aspects of the dataset, such as types, attributes, generations, and more. The analysis includes visualizations and insights into different subsets of Pokemon based on their types.

## Dataset

The dataset used in this project is named "Pokemon.csv". It contains information about different Pokemon, including their primary and secondary types, attributes like HP, speed, attack, defense, and more. The dataset is in CSV format and is loaded using the `readr` library.

## Analysis

The project performs the following analyses on the Pokemon dataset:

- Information about the dataset, including the number of rows, columns, and missing values.
- Types and number of Pokemons: A treemap visualization shows the distribution of Pokemon types and their counts.
- Types and total attributes: A bar chart displays the average total attributes for each type.
- Generations: A pie chart illustrates the distribution of Pokemon across different generations.
- Legendary status: A bar chart presents the number of legendary and non-legendary Pokemon.
- Physical abilities: Information about the minimum and maximum values of special attack (Sp. Atk), special defense (Sp. Def), and HP attributes.

The analysis further focuses on specific types of Pokemon, such as Grass, Fire, and Water, providing insights into their attributes, legendary status, generation distribution, and more.

## Usage

To run this project, follow these steps:

1. Install the required R packages: `readr`, `RColorBrewer`, `ggplot2`, `treemapify`, and `dplyr`.
2. Place the "Pokemon.csv" file in the same directory as the R script.
3. Open the R script in an R environment (e.g., RStudio).
4. Run the script line by line or as a whole to perform the analysis.
5. Review the generated visualizations and insights.

Feel free to modify the code or explore additional analyses based on your requirements.

## Dependencies

This project relies on the following R packages:

- `readr`: For reading the CSV dataset.
- `RColorBrewer`: For color palettes in visualizations.
- `ggplot2`: For creating visualizations.
- `treemapify`: For creating treemap visualizations.
- `dplyr`: For data manipulation.

Ensure that these packages are installed before running the script.
