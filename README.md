### Business Context
*	[LendingClub](https://www.lendingclub.com/) is one of the world's largest peer-to-peer lending platforms providing loans and investment opportunities for individual and corporate customers.
*	In the recent years, the share of defaulted loans issued on the platform has increased significantly, therefore the company seeks to develop a predictive model of default to support the underwriting process.
*	Aim of the project is to increase detection of defaulted loans before the loan is issued/offered on the platform, so model score can be used as an additional input in application assessment process.

### Dataset
*	The open-sourced authentic [dataset](https://www.kaggle.com/wendykan/lending-club-loan-data/downloads/lending-club-loan-data.zip) contains records of ~2.2M clients who borrowed money on the platform between 2007-2018.
*	Information is stored in 145 columns, some of which are filled only once (e.g. at the time of application or only in the case of a particular event occurring), some updated periodically with only most recent value present.
*	Default client is defined as one with *loan_status* variable taking on the following levels: *Charged off*, *Default*, *Late (31-120 days)* and *Does not meet the credit policy. Status: Charged Off*.
*	About 40% of the data points correspond to current loans, which are neither default nor fully paid.
* Defaulted loans constitute only about 12.5% of the whole dataset.

### Challenges
* The data comes from an actual company and the collection process in general was not consistent, therefore thorough preprocessing is required.
* Some columns were edited after the loan was issued which can lead to data leakage if these columns are not discarded before fitting the models.
* Dataset has missing values.
* Some columns contain categorical variables with many levels.
* There is a significant number of possibly irrelevant features, so the best features have to be methodically selected.
* Class imbalance has to be addressed.

### Solution
* Prepared several competing predictive models of default.
* We perform model selection by comparing average ROC and AUC computed via 5-fold cross-validation.
*	The top performing model achieves AUC > 0.7.
* Among considered models were: logistic regression, decision tree, boosted tree, random forest, gaussian naïve Bayes and SVM classifiers.
