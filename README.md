<img src="./images/titlepic.jpg" alt="Democratizing Autonomous Driving" style="height: 310px; width:660px;"/>

# Real Estate Statistical Modeling with Feature Engineering


**Problem Statement:** The tech savvy daughter of a real estate tycoon acquired property by inheritance of her late mother’s assets. Data-driven insights were requested to make informed decisions regarding the sale of, or investment in, each property to maximize profit between the years 2006-2010.

**Exploration of the following specific questions:**
* Are location and size the most important factors in the final sale price of a home?
* What can a property owner do to improve home value?

---
### Contents

* [EDA & Data Cleaning](#eda_and_cleaning)
* [Preprocessing & Feature Engineering](#preprocessing_and_feature_engineering)
* [Model Benchmarks](#model_benchmarks)
* [Model Tuning](#model_tuning)
* [Production Model & Insights](#production_model_and_insights)
* [Recommendations and Next Steps](#recommendations_and_next_steps)
* [Kaggle Submissions](#kaggle_submissions)
* [Software Requirements](#software_requirements)
* [Acknowledgements and Contact](#acknowledgements_and_contact)


<a id='eda_and_cleaning'></a>

---
### EDA & Data Cleaning - Notebook 01

### Datasets

#### Raw Data

* [`test.csv`](./data/datasets/test.csv): Journal of Statistics Education ([source](http://jse.amstat.org) | [data dictionary](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt))
* [`train.csv`](./data/datasets/train.csv): Journal of Statistics Education ([source](http://jse.amstat.org) | [data dictionary](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt))

#### Processed Data
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


**Notes about the data:**
    -Time was spent searching for null values, dropping outliers, and recognizing the simplest approach was a first model with only integer features.

    **Select Categorical Features from Ames housing Data Set**
    > 1. Referring to Data Library for definitions of sub-categorical features, follow best judgement for an initial prediction to beat the baseline Null.
    > 2. Guess and check with boxplots in Notebook 02, returning back to feature selection to adjust paramaters.
    > 3. I chose the following values initially based on what made sense to me, then following feedback from statsmodels in Notebook 03 I interpretted p-values to improve my RMSE computed in Notebook 04

#### EDA
- Determine _what_ missing values mean.
- Figure out what each categorical value represents.
- Identify outliers.
- Consider whether discrete values are better represented as categorical or continuous. (Are relationships to the target linear?)

#### Data Cleaning
- Decide how to impute null values.
- Decide how to handle outliers.
- Do you want to combine any features?
- Do you want to have interaction terms?
- Do you want to manually drop collinear features?

<a id='preprocessing_and_feature_engineering'></a>

---
### Pre-Processing and Feature Engineering - Notebook 02

***Pre-processing***
> * Set-up Models
>* One-hot encode categorical variables
>* Train/test split the data
>* Scale the data
>* Consider using automated feature selection


<a id='model_benchmarks'></a>

---
### Model Benchmarks and Preparation - Notebook 03


<a id='model_tuning'></a>

---
### Model Tuning & Assessment - Notebook 04


<a id='production_model_and_insights'></a>

---
### Production Model & Insights - Notebook 05


<a id='recommendations_and_next_steps'></a>

---
### Recommendations and Next Steps


<a id='kaggle_submissions'></a>

---
### Kaggle Submissions - Notebook 06


<a id='software_requirements'></a>

---
### Software Requirements


<a id='acknowledgements_and_contact'></a>

---
### Acknowledgements and Contact:

External Resources:
* [`Title`] (Platform): ([*source*](https://www.URL.com))

Papers:
* `Title` (Journal/Blog): ([*source*](https://www.URL.com))

Contact:

> * Brandon Griffin [GitHub](https://github.com/griffinbran) | [LinkedIn](https://www.linkedin.com/in/griffinbran/) | [Twitter](https://twitter.com/GriffinBran) | [Medium](https://griffinbran.medium.com)
---