# Case study about the influence of social dimensions on solvency scores
This repository contains the analysis and resulting master thesis "Empirical Study about the Influence of Social Dimensions on the SCHUFA-Score".

## The data set and the openSCHUFA project
The unstructured form of the SCHUFA-reports and the structured questionnaire data was provided by the openSCHUFA project which consisted of the AlgorithmWatch Initiative and the Open Knowledge Foundation in 2018.
A very time-consuming process to again convert the data into structured data had been done by the editors of the data teams of SPIEGEL Online and Bayerischer Rundfunk (BR). This extracted form of structured data, combined with the data of the questionnaire, was then provided by the data journalists of SPIEGEL Online for this thesis.

## The Goal of the study

The goal of the study is to analyse the influence of selected social dimensions on the different versions of selected sector scores of the SCHUFA solvency score. This is meant to start a discussion on how algorithmic systems potentially take part in reproducing a disparate distribution of resources by explicitly using or implicitly reflecting social dimensions in the output they produce. What parts of it do we as a society accept and what needs to be taken into account by the constructors and users of such algorithms.

## The approach

1. Clean the data set
	1. Check for duplicates
	2. Filter invalid data
	3. Remove outliers
	4. Remove score values that are invalid

2. Create features from questionaire and SCHUFA-Auskunft

3. Univariate descriptive analysis
	1. Analyse frequency distributions of all features
	2. Analyse representation biases in the data by comparing social feature relative frequencies with German population
	3. Analyse frequency distributions of solvency scores and the respective versions to select two sector scores: Banking and Mail Order

4. Bivariate descriptive analysis
	1. Analyse associations between social and financial features
	2. Analyse associations between social features and selected solvency scores

5. Feature preprocessing
	1. Score Transformation for versions 2 and 3 using the log Function
	2. Conversion of categorical, ordinal and metric features
	3. Standardization of metric data

6. Subsampling w.r.t. chosen social dimensions (age, sex, historical east/west germany)
	1. Analyse correlations to check which covariates may mediate an effect
	2. Apply matching algorithm to obtain similar distributions of covariates. This enables us to compare only attributes that are present in all groups w.r.t. a social dimension

7. Multivariate analysis
	1. Feature engineering to account for interactions and feature selection to only use relevant features
	2. Parametric approach: Multivariate linear regression to analyse the influence of selected social dimensions according to the respective coefficients as well as the variance explained
	3. Non-parametric approach: Gaussian process to analyse the variance explained by a social dimension
	4. Visualize the influences: Show the influence of social dimensions over the different versions of the selected sector scores

