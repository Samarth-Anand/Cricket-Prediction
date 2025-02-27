# Predicting the Best Indian Premier League Fantasy Team using Machine Learning and Deep Learning
This repository contains a comprehensive machine learning project aimed at predicting the best fantasy team for the Indian Premier League (IPL) using advanced data analysis and neural network techniques. Developed by Dr. Siddharth between January 2024 and December 2024, this project leverages historical IPL data to enhance fantasy team selection by predicting player performance metrics with high accuracy.

Project Overview
The primary goal of this project is to utilize machine learning to improve IPL fantasy team selection by analyzing player performance across batting, bowling, and fielding dimensions. The solution integrates a robust feature engineering pipeline to extract player statistics and employs a custom neural network architecture combining LSTM layers and attention mechanisms to predict future points. The project achieves a significant 60% error reduction compared to traditional models, making it a valuable tool for fantasy cricket enthusiasts.

Key Features
Advanced Feature Engineering Pipeline: Extracts and standardizes critical player metrics such as batting averages, strike rates, bowling averages, economy rates, and boundary frequencies for players with a minimum of 200 balls faced or bowled.
Custom Neural Network Architecture: Combines LSTM layers, multi-head attention mechanisms, and specialized branches for predicting batting, bowling, and fielding points, optimizing performance predictions across different aspects of the game.
Superior Performance: Achieves a 60% error reduction over baseline approaches (e.g., Feedforward Neural Networks, Random Forest), with an overall RMSE of 18.793 on test data.
Technical Details
Data
Source: IPL ball-by-ball and match data from 2008 to 2022 (IPL_Ball_by_Ball_2008_2022.csv and IPL_Matches_2008_2022.csv).
Preprocessing:
Handles team name changes (e.g., Delhi Daredevils to Delhi Capitals).
Removes rain-affected or abandoned matches to ensure data integrity.
Calculates standardized player statistics (e.g., batting averages, strike rates, bowling economy) based on a 200-ball threshold.
Feature Engineering
The project computes a variety of player performance metrics, including:

Batting: Averages, strike rates, balls faced, centuries, half-centuries, fours/sixes per innings, dot ball percentage, boundary frequency.
Bowling: Averages, balls per wicket, wickets per game, economy rate, dot ball percentage, sixes/fours conceded per over, overs per match, boundary frequency.
These features are standardized and merged into a comprehensive dataset for model training.

Model Architecture
Framework: Implemented in PyTorch.
Components:
LSTM Layers: Capture temporal dependencies in player performance sequences (default sequence length: 5 matches).
Multi-Head Attention: Enhances focus on relevant sequence elements.
Specialized Branches: Separate prediction heads for batting, bowling, and fielding points.
Training:
Uses AdamW optimizer with learning rate scheduling (OneCycleLR).
Employs early stopping with a patience of 10 epochs to prevent overfitting.
Trained on a sequence-based dataset with batch size 32 over 100 epochs (configurable).
Evaluation Metrics
Overall Performance:
MSE: 353.169
RMSE: 18.793
MAE: 12.169
Per-Point Type Performance:
Batting: MSE: 663.844, RMSE: 25.765, R²: 0.130, Correlation: 0.472
Bowling: MSE: 371.799, RMSE: 19.282, R²: 0.194, Correlation: 0.528
Fielding: MSE: 23.862, RMSE: 4.885, R²: 0.021, Correlation: 0.200
Conclusion
This project demonstrates a sophisticated approach to predicting IPL fantasy team performance using machine learning. By leveraging a custom neural network with LSTM layers, multi-head attention, and specialized branches, it outperforms traditional models like Feedforward Neural Networks, LSTM, Random Forest, and others by achieving a 60% error reduction with an RMSE of 18.793. The detailed feature engineering pipeline ensures robust data preprocessing and metric extraction, making this a powerful tool for fantasy cricket enthusiasts.
