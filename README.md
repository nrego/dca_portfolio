# DCA Backtesting Tool

Adapted by NBR, 02/28/2024

## Overview
This tool provides a comprehensive simulation of a Dollar-Cost Averaging (DCA) investment strategy, allowing for backtesting against historical stock data. Users can test strategies based on investing a fixed amount into the 'k' lowest-performing stocks over a defined lookback period. Features include adjustable lookback and investment cadence periods, and the ability to specify overweight/underweight investment allocations.

## Files
- dca_portfolio.ipynb : Main Jupyter Notebook - Run this to execute DCA simulations
- Copy_of_dcs_portfolio.ipynb : Initial version of code, for reference (note - this code is broken)
- ./sample_stocks/ : Directory containing text files with sample stock universes

## Installation
The tool is designed to work with Anaconda's Python 3.x distribution for ease of use and installation:

1. Download the latest version of the code from [GitHub](https://github.com/nrego/dca_portfolio/).
2. From the root directory of the project, create and activate a custom Python Conda environment using the provided "environment.yaml" file:

```bash
conda env create -f environment.yaml
conda activate dca_portfolio
```

3. (Optional) Create a Jupyter Notebook kernel named "dca_portfolio":

```bash
python -m ipykernel install --user --name dca_portfolio --display-name "Python (dca_portfolio)"
```

## Usage
To use the DCA backtesting tool:

1. Launch Jupyter Notebook from the root directory:

```bash
jupyter notebook
```

2. Open the "dca_portfolio.ipynb" notebook and select the "Python (dca_portfolio)" kernel.
3. Run all cells in the notebook to initialize the tool.
4. At the bottom of the notebook, use the GUI to input your simulation parameters and run the simulation:

    - Upload a list of stock ticker symbols (plain text file, one ticker per line). Sample files can be found in "./sample_stocks/".
    - Enter your FMP API key (optional).
    - Specify the investment amount per period, number of stocks (`k`), loss threshold (in percent), overweight allocation (in percent), lookback period (in months), and investment period (in months).
    - Click "Run Simulation" to start the backtesting process. This might take a while as it downloads historical data and performs the simulation.

## Results Visualization
The tool provides two main tabs for results visualization:

- **Equity Graph**: Plots the simulated performance of your investment strategy over time, comparing it to a baseline strategy of equally investing in all stocks each period.
- **Cohorts and Strategy**: Displays a DataFrame illustrating the performance of each investment cohort over time, including the aggregate performance of all cohorts.
- **Download Results**: Allows you to download detailed results as Excel files, including the investment strategy performance and selection history.

