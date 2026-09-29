# Market Microstructure & Liquidity Risk: HMMs and Queueing Theory

## Overview
This repository investigates the mechanical failure of exchange infrastructure during high-frequency market crashes using limit order book data from the Optiver dataset. By bridging empirical data science with theoretical systems engineering, the analysis models the exact moments when algorithmic buyers withdraw from the market and create a severe liquidity vacuum.

## Methodology
* **Data Engineering:** The pipeline processes raw parquet limit order book data to calculate the queue imbalance ratio based on resting bid and ask sizes. To bypass single-thread CPU limits, the continuous time series is chronologically grouped by isolated time sequences and capped at 50,000 rows.
* **Unsupervised Regime Detection:** A 2-state Gaussian Hidden Markov Model (HMM) dynamically clusters the market into "Calm Market" and "Buy-Side Vacuum" regimes based on the average imbalance.
* **Empirical Queue Failure:** The physical server load is evaluated by calculating the median ask and bid queue backlogs to quantify the exact queue discrepancy and server failure during a crash.
* **Theoretical vs. Physical Simulation:** A discrete-event simulation compares a theoretical infinite M/M/1 queue against a physical M/M/1/K queue with a server memory limit of 150. The simulation utilizes Poisson distributions for arrival and service rates to graph the exact moment the server buffer saturates and begins rejecting orders.

## Technologies Used
* **Python**, **Pandas**, and **NumPy** for vectorized logic and high-frequency data engineering.
* **hmmlearn** for Expectation-Maximization and Gaussian HMM regime detection.
* **Matplotlib** for synthetic queue divergence and regime switching visualization.# Market Microstructure & Liquidity Risk: HMMs and Queueing Theory

## Overview
This repository investigates the mechanical failure of exchange infrastructure during high-frequency market crashes using limit order book data from the Optiver dataset. By bridging empirical data science with theoretical systems engineering, the analysis models the exact moments when algorithmic buyers withdraw from the market and create a severe liquidity vacuum.

## Methodology
* **Data Engineering:** The pipeline processes raw parquet limit order book data to calculate the queue imbalance ratio based on resting bid and ask sizes. To bypass single-thread CPU limits, the continuous time series is chronologically grouped by isolated time sequences and capped at 50,000 rows.
* **Unsupervised Regime Detection:** A 2-state Gaussian Hidden Markov Model (HMM) dynamically clusters the market into "Calm Market" and "Buy-Side Vacuum" regimes based on the average imbalance.
* **Empirical Queue Failure:** The physical server load is evaluated by calculating the median ask and bid queue backlogs to quantify the exact queue discrepancy and server failure during a crash.
* **Theoretical vs. Physical Simulation:** A discrete-event simulation compares a theoretical infinite M/M/1 queue against a physical M/M/1/K queue with a server memory limit of 150. The simulation utilizes Poisson distributions for arrival and service rates to graph the exact moment the server buffer saturates and begins rejecting orders.

## Technologies Used
* **Python**, **Pandas**, and **NumPy** for vectorized logic and high-frequency data engineering.
* **hmmlearn** for Expectation-Maximization and Gaussian HMM regime detection.
* **Matplotlib** for synthetic queue divergence and regime switching visualization.
