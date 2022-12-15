Portfolio Optimizer
Adam Suhajda
Abstract
Elastic Net and LSTM Artificial Neural Net models were fitted for each portfolio constituent to predict their T1 returns. For Elastic Net, 5-fold validation was used, 2-fold validation if sample size was less than 4 records. LSTM Neural Net used 20% of the data for validation, rectified linear units for activation, ADAM for weight optimization, a max of 20 epochs or 4 as early stopping parameter. Both models were evaluated based on MAPE. Elastic Net performed better with a mean mape of 255.6 vs 396.3 of LSTM. Therefore considering the T1 forecasts from Elastic Net, assets with negative expected returns were disposed from portfolio. Random weights were then assigned to each asset 5.000 times and Information Ratio(IR) was calculated for each experiment. Portfolio weights were rebased daily to mitigate fluctuation of constituents over time. Portfolio with best IR of 53.15 was identified. Using kmeans, simulation results were also categorized into 3 categories based on their annualized return(AR): high, medium and low return categories. Best portfolios were identified for each category, potentially help suggesting the best selection for different risk appetites (high-return category IR:53.13, AR:0.109534; medium-return: IR:53.15, AR:0.109112; low-return: IR:50.810544, AR:0.103923). 252 trading days were assumed per year for annualization.

Caveats and research assumptions
Portfolio weights sum up to 1 daily to mitigate changes of constituents over time. This assumes full capital investment every day.
Empirical results showed better model fit when forward and backfilling features compared to only filling NANs with 0s, hence assumption was made it is logically sound.
Based on brief provided, it was assumed T0 returns can't be used as predictor.
In case of some IDs, predictions were stale or gravitated closely to the average of the T1 return, suggesting poor explanation power of features over "y". In a live environment I would entertain the idea of expanding the feature set (f.e. with macroeconomic news data).
It was observed LSTM Neural Network could improve MAPE significantly via more training epochs and/or higher early stopping parameter. Limited computation capacity didn't allow this optimization for the experiment.
Early stopping doesn't guarantee best model selection as it can stop training not at the closest fit. In a live environment and to improve mape, I would recommend saving the models and selecting the one with best performance.
Chapter 1 - Set environment
