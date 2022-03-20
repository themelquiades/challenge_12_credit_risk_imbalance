# Determining Creditworthiness with Supervised Machine Learning
Week 12 Challenge, using a dataset of historical lending activity from a peer-to-peer lending services company to build logistic regression models that can identify the quality/riskiness of a loan.

## Overview

Credit risk results in an inherently imbalanced classification problem since healthy loans normally outnumber risky loans. To acknowledge and solve for this imbalance, this analysis runs logistic regression models on a raw and an oversampled dataset of historical lending activity to determine which version better predicts creditworthiness of loans.

The lending data inputs included loan size, interest rate, borrower income, debt to income, number of accounts, derogatory marks, and total debt. These factors were used to predict whether a loan was healthy or high-risk.

Out of the 77,536 loans in the original dataset, only 2,500 were marked as high-risk, causing an imbalance that could bias a logistic regression model. 

To ensure a well-fit model, a LogisticRegression was performed on both the original dataset and a dataset resampled using RandomOverSampler.

For each sample, the data was split into training and test data. The machine learning model was then created, fit to the training data, and used to predict whether the test loans were healthy or high-risk.

The accuracy of each model was then tested using a balanced accuracy score, a confusion matrix, and an imbalanced classification table.


## Results

* Machine Learning Model 1 (Original Data):
  
  * Balanced accuracy score = 95%, however this may be misleading since the dataset was so imbalanced. 
  * Precision: Healthy = 100%; High-Risk = 85%
  * Recall: Healthy = 99%; High-Risk = 91%

* Machine Learning Model 2 (Resampled Data using RandomOverSampler):
  
  * Balanced accuracy score = 99% 
  * Precision: Healthy = 100%; High-Risk = 84%
  * Recall: Healthy = 99%; High-Risk = 99%  
  
## Summary

Overall, oversampling seemed to improve the logistic regression model. The accuracy score was higher, at over 99% using oversampled data compared to 95% using the original. When looking at the imbalanced classification report, we saw that the oversampled model again predicted 0s (healthy loans) with 100% precision, but 1s (high-risk loans) with 84% precision, slightly lower than when training with the original data. However, recall in the oversampled model was 99% when predicting both the healthy and the high-risk loans, much better than the respective 99% and 91% using the original data. This is the most important metric since one wants to be sure her or she is correctly identifying as many high-risk loans (1s) as possible.


## Contributors

This analysis was created by Nico Cortese with support from the lovely Fintech Coding Boot Camp Team at Boot Camp Spot / Columbia School of Engineering

Nico Cortese

XXX-XXX-XXXX

XXXX@gmail.com

---

## License

MIT License

Copyright (c) 2022 NicoCortese

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
