# Project 2 - Ames Housing Data and Kaggle Challenge

Welcome to Project 2! It's time to start modeling.

**Target Audience:** A tech savvy daughter of a real estate tycoon has recently inherited her late mother’s assets. She hired me to run an OLS regression analysis to help her maximize profit while selling her homes in Iowa as she heads to Florida for early retirement. Yay.

**Problem Statement:**

    -Are location and size the most important factors in the final sale price of a home?

---

### Datasets

#### Provided Data

* [`test.csv`](./data/datasets/test.csv): Ames, IA Real Estate Data 2006-2010 ([source](http://jse.amstat.org) | [data dictionary](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt))
* [`train.csv`](./data/datasets/train.csv): Ames, IA Real Estate Data 2006-2010([source](http://jse.amstat.org) | [data dictionary](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt))

#### Additional Datasets
* [`clean_train.csv`](./data/datasets/test.csv): Subset of train.csv after cleaning in Notebook 01, saved for use in all notebooks.
* [`cat_select_test_m4.csv`](./data/datasets/test.csv): Subset of data from categorical features included in Model 4, saved for Kaggle submission.
* [`cat_select_train.csv`](./data/datasets/test.csv): Subset of data from categorical features included in Model 4, saved for Kaggle submission.

### Data Dictionary

|Feature|Type|Dataset|Category|Description|
|---|---|---|---|---|
|**Bldg TypeC**|*integer*|2006-10<br>Ames, Iowa<br>Assessor’s Office|'1Fam':0<br>'TwnhsE':0<br>'Twnhs':1<br>'2fmCon':1<br>'Duplex':1|Type of building|
|**Central AirC**|*integer*|2006-10<br>Ames, Iowa<br>Assessor’s Office|'Y':0, 'N':1|Central Air-Conditioning|
|**Condition 1C**|*integer*|2006-10<br>Ames, Iowa<br>Assessor’s Office|0: Other, 1:Near/adjacent to major streets/Railroads, 2:Near/Adjacent to poz off-site feature|Proximity to various conditions|
|**Exterior 1stC**|*integer*|2006-10<br>Ames, Iowa<br>Assessor’s Office|Asbestos Shingles:1, else:0|Exterior covering on house|
|**Exter QualC**|*integer*|2006-10<br>Ames, Iowa<br>Assessor’s Office|Good/Typical:0, Fair:1, Excellent:2|Quality of material on exterior|
|**FoundationC**|*integer*|2006-10<br>Ames, Iowa<br>Assessor’s Office|CinderBlock/Stone/Wood:0, Brick/Slab:1, PouredConcrete:2|Type of Foundation|
|**Land ContourC**|*integer*|2006-10<br>Ames, Iowa<br>Assessor’s Office|Banked-Quick and significant rise from street grade to building:1, Other:0|Flatness of the property|
|**Lot ConfigC**|*integer*|2006-10<br>Ames, Iowa<br>Assessor’s Office|Cul-de-sac:1, Other:0|Lot Configuration|
|**Lot ShapeC**|*integer*|2006-10<br>Ames, Iowa<br>Assessor’s Office|Most Irregular: 1, Otherwise:0|General shape of property|
|**1st Flr SF**|*integer*|2006-10<br>Ames, Iowa<br>Assessor’s Office|Continuous|First Floor Square-Feet|
|**Garage Area**|*integer*|2006-10<br>Ames, Iowa<br>Assessor’s Office|Continuous|Size of garage in Square-Feet|
|**Gr Liv Area**|*integer*|2006-10<br>Ames, Iowa<br>Assessor’s Office|Continuous|Above grade living area in Square-Feet|
|**Heating QCC**|*integer*|2006-10<br>Ames, Iowa<br>Assessor’s Office|_1:No 2:Yes|Heating Quality & Condition|
|**NeighborhoodC**|*integer*|2006-10<br>Ames, Iowa<br>Assessor’s Office| 2: StoneBr, NridgHt, NoRidge<br>1: Sawyer, BrDale, IDOTRR, MeadowV, SWISU, BrkSide, NPkVill, Blueste, Landmrk<br>0: All others|Physical locations within the Ames city limits classified by sample average-'Sale Price'.<br>Class 0 avg Sale Prices were less than 1 stdev above/below the sample avg., Class 02 were above, Class 01 below.|
|**Overall Qual**|*integer*|2006-10<br>Ames, Iowa<br>Assessor’s Office|Ordinal: 10-Very Excellent to 1-Very Poor|Overall quality of material and finish|
|**Paved DriveC**|*integer*|2006-10<br>Ames, Iowa<br>Assessor’s Office| 1:No/Partial, 0:Yes|Paved driveway|
|**Total Bsmt SF**|*integer*|2006-10<br>Ames, Iowa<br>Assessor’s Office|Continuous|Total Square-Feet of Basement Area|
|**Year Built**|*integer*|2006-10<br>Ames, Iowa<br>Assessor’s Office|Discrete, range: 1872 - 2010|Original Construction Date|
|**Year Remod/Add**|*integer*|2006-10<br>Ames, Iowa<br>Assessor’s Office|Discrete, range: 1950 - 2010|Remodel date or construction date if no remodel or additions|



---

## Notebook 01: Data Cleaning and EDA

**Notes about the data:**
    -Time was spent searching for null values, dropping outliers, and recognizing the simplest approach was a first model with only integer features.

    **Select Categorical Features from Ames housing Data Set**
    1. Referring to Data Library for definitions of sub-categorical features, follow best judgement for an initial prediction to beat the baseline Null.
    2. Guess and check with boxplots in Notebook 02, returning back to feature selection to adjust paramaters.
    3. I chose the following values initially based on what made sense to me, then following feedback from statsmodels in Notebook 03 I interpretted p-values to improve my RMSE computed in Notebook 04
---

## Notebook 02: Pre-Processing and Feature Engineering
***Pre-processing***
Set-up Models
One-hot encode categorical variables.
Train/test split your data.
Scale your data.
Consider using automated feature selection.
---

## Notebook 03: Model Benchmarks and Preparation
---

## Notebook 04: Model Tuning, Scoring, and Assessment