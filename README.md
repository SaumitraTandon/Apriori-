# Apriori Algorithm for Market Basket Analysis

This project demonstrates the implementation of the Apriori algorithm, a classic algorithm used for association rule learning in the context of Market Basket Analysis. The goal is to identify the sets of products that frequently appear together in transactions.

## Project Overview

- **Apriori Algorithm**: The Apriori algorithm is used to identify item sets that frequently appear together and to generate association rules with specified minimum support, confidence, and lift.
- **Market Basket Analysis**: This is a key technique used by large retailers to uncover associations between items. The insights can help in making strategic decisions such as product placement, promotions, etc.

## Getting Started

### Prerequisites

You need to have the following libraries installed:

```bash
pip install apyori
```

Additionally, the project requires standard data manipulation and visualization libraries:

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
```

### Installation

1. Clone the repository to your local machine:

    ```bash
    git clone https://github.com/yourusername/your-repository.git
    cd your-repository
    ```

2. Install the required Python packages:

    ```bash
    pip install -r requirements.txt
    ```

3. Ensure you have the dataset named `Market_Basket_Optimisation.csv` in your project directory.

### Running the Project

The project is structured as a Jupyter notebook. You can run it step-by-step as follows:

1. **Data Preprocessing**: The dataset is loaded and processed into a format suitable for the Apriori algorithm.

    ```python
    dataset = pd.read_csv('Market_Basket_Optimisation.csv', header=None)
    transactions = []
    for i in range(0, 7501):
        transactions.append([str(dataset.values[i,j]) for j in range(0, 20)])
    ```

2. **Training the Apriori Model**: The Apriori model is trained using the processed transaction data.

    ```python
    from apyori import apriori
    rules = apriori(transactions=transactions, min_support=0.003, min_confidence=0.2, min_lift=3, min_length=2, max_length=2)
    ```

3. **Visualizing the Results**: The generated association rules are visualized and sorted to identify the most significant ones.

    ```python
    results = list(rules)
    ```

    You can also organize the results into a Pandas DataFrame and sort them by lift:

    ```python
    resultsinDataFrame.nlargest(n=10, columns='Lift')
    ```

## Project Structure

- `apriori.ipynb`: The main Jupyter notebook containing the implementation.
- `Market_Basket_Optimisation.csv`: The dataset used for training the model.
- `README.md`: Project documentation.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request with your suggestions or improvements.
