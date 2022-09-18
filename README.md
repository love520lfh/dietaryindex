## dietaryindex

### Overview
___

Version 0.10.0: now support DHQ3 for AHEI, MED, HEI2015 and DASH. DII is avaiable as a generic function. DII with and without alcohol overall and components score are available.

The main goal of this package **dietaryindex** is for calculating different dietary pattern indexes or scores easily and conveniently. 

**dietaryindex** calculates dietary indexes by 2 steps:
1. Calculate the serving size of each food and nutrient category
2. Calculate the individual dietary index

Currently, the **dietaryindex** package works for the following 5 dietary assessment tools to calculate many dietary indexes within 1 steps:
1. It can calculate HEI2015, AHEI, AHEIP, DASH, DASHI, MED, MEDI, and DII for the Block FFQ. 
2. It can calculate HEI2015, AHEI, DASH, MED, and DII for the NHANES_FPED (after 2005).
3. It can calculate HEI2015, AHEI, DASH, MED, and DII for the ASA24
4. It can calculate HEI2015, AHEI, DASH, MED for the DHQ3
5. It can calculate HEI2015 for the NIH-AARP

This package can also help you calculating these dietary pattern indexes (HEI2015, AHEI, AHEIP, DASH, DASHI, MED, MEDI, DII) using all other dietary assessments, if you provide the relevant serving sizes for each food/nutrient category.
- All you need to do is to provide the relevant serving sizes for each food/nutrient category in the index.
- The excel sheet for the serving size of all dietary indexes is provided: DIETARYINDEX_SERVING_SIZE_CHART_JAMES_ZHAN.xlsx


The **dietaryindex** package relies on the **dplyr**, **readr**, and **haven** packages. Please install them ahead.

### Installation
___

**dietaryindex** is currently not available on [CRAN]


To install the development version hosted on this GitHub repository, use the **devtools** package and the following:

```
install.packages("devtools") #If you don't have "devtools" installed already
devtools::install_github("jamesjiadazhan/dietaryindex")
```

To install **dplyr**, **readr**, and **haven** packages if you are new to R or don't have them, use the following:
```
install.packages("dplyr")
install.packages("readr")
install.packages("haven")
```

### Getting Started
___
```
library(dietaryindex)
library(dplyr)
library(readr)
library(haven)
```

The **dietaryindex** package currently contains the following key functions:
>`HEI2015()`, Healthy Eating Index 2015 (https://www.fns.usda.gov/how-hei-scored)

>`AHEI()`, alternative healthy eating index (https://pubmed.ncbi.nlm.nih.gov/22513989/)

>`AHEIP()` , alternative healthy eating index - pregnancy (https://pubmed.ncbi.nlm.nih.gov/19465182/)

>`DASH()`, Dietary Approaches to Stop Hypertension (https://pubmed.ncbi.nlm.nih.gov/18413553/)

>`DASHI()`, Dietary Approaches to Stop Hypertension Index (modified from multiple sources to provide most updated serving size-based DASH index, including https://www.nhlbi.nih.gov/education/dash-eating-plan, https://pubmed.ncbi.nlm.nih.gov/17324731/, https://www.dietaryguidelines.gov/sites/default/files/2020-12/Dietary_Guidelines_for_Americans_2020-2025.pdf, https://jamanetwork.com/journals/jamainternalmedicine/fullarticle/414155, https://www.nejm.org/doi/full/10.1056/nejm199704173361601)

>`MED()`, Mediterranean diet (https://pubmed.ncbi.nlm.nih.gov/33574608/)

>`MEDI()`, Mediterranean diet index, serving size-based (https://pubmed.ncbi.nlm.nih.gov/28160450/)



>`HEI2015_BLOCK()`, Calculate the HEI2015 dietary index with 1 step for the Block FFQ per 1 day

>`AHEI_BLOCK()`, Calculate the AHEI dietary index with 1 step for the Block FFQ per 1 day

>`AHEIP_BLOCK()` ,Calculate the AHEIP dietary index with 1 step for the Block FFQ per 1 day

>`DASH_BLOCK()`, Calculate the DASH dietary index with 1 step for the Block FFQ per 1 day

>`DASHI_BLOCK()`, Calculate the DASHI dietary index with 1 step for the Block FFQ per 1 day

>`MED_BLOCK()`, Calculate the MED dietary index with 1 step for the Block FFQ per 1 day

>`MEDI_BLOCK()`, Calculate the MEDI dietary index with 1 step for the Block FFQ per 1 day

>`DII_BLOCK()`, Calculate the DII dietary index with 1 step for the Block FFQ per 1 day



>`HEI2015_AARP()`, Calculate the HEI2015 dietary index for the NIH-AARP per 1 day



>`HEI2015_NHANES_FPED()`, Calculating the serving sizes for HEI2015 with 1 step using the NHANES_FPED data (after 2005)

>`AHEI_NHANES_FPED()`, Calculating the serving sizes for AHEI with 1 step using the NHANES_FPED data (after 2005)

>`DASH_NHANES_FPED()`, Calculating the serving sizes for DASH with 1 step using the NHANES_FPED data (after 2005)

>`MED_NHANES_FPED()`, Calculating the serving sizes for MED with 1 step using the NHANES_FPED data (after 2005)

>`DII_NHANES_FPED()`, Calculating the serving sizes for DII with 1 step using the NHANES_FPED data (after 2005)



>`HEI2015_ASA24()`, Calculating the serving sizes for HEI2015 with 1 step using the ASA24 data

>`AHEI_F_ASA24()`, Calculate the AHEI (female only) within 1 step using the ASA24 data

>`AHEI_M_ASA24()`, Calculate the AHEI (male only) within 1 step using the ASA24 data

>`DASH_ASA24()`, Calculating the serving sizes for DASH with 1 step using the ASA24 data

>`MED_ASA24()`, Calculating the serving sizes for MED with 1 step using the ASA24 data

>`DII_ASA24()`, Calculating the serving sizes for DII with 1 step using the ASA24 data


>`HEI2015_DHQ3()`, Calculating the serving sizes for HEI2015 with 1 step using the DHQ3 data

>`AHEI_DHQ3()`, Calculate the AHEI (female or male) within 1 step using the DHQ3 data

>`DASH_DHQ3()`, Calculating the serving sizes for DASH with 1 step using the DHQ3 data. The data is Detailed analysis file, ending with detail.csv

>`MED_DHQ3()`, Calculating the serving sizes for MED with 1 step using the DHQ3 data


### Examples:
___
#### Calculating HEI2015 for ASA24
```
DATA_PATH = "/Users/james/Desktop/data/Totals.csv"
HEI2015_ASA24(DATA_PATH)

#Use the example data
data("ASA24_exp")
HEI2015_ASA24(ASA24_exp)
```

#### Calculating HEI2015 for DHQ3
```
DATA_PATH = "/Users/james/Desktop/data/results.csv"
HEI2015_DHQ3(DATA_PATH)

#Use the example data
data("DHQ3_exp")
HEI2015_DHQ3(DHQ3_exp)
```

#### Calculating AHEI for DHQ3
```
DATA_PATH = "/Users/james/Desktop/data/detail.csv"
AHEI_DHQ3(DATA_PATH)

#Use the example data
data("DHQ3_exp_detailed")
AHEI_DHQ3(DHQ3_exp_detailed)
```

#### Calculating DASH for DHQ3
```
DATA_PATH = "/Users/james/Desktop/data/detail.csv"
DASH_DHQ3(DATA_PATH)

#Use the example data. Attention: the example data here is DHQ3_exp_detailed, which is different from DHQ3_exp. DHQ3_exp_detailed is only used for DASH_DHQ3
data("DHQ3_exp_detailed")
DASH_DHQ3(DHQ3_exp_detailed)
```

#### Calculating HEI2015 for NHANES_FPED
```
FPED_PATH = "/Users/james/Desktop/fped_dr1tot_1718.sas7bdat"
NUTRIENT_PATH = "/Users/james/Desktop/DR1TOT_J.XPT"
DEMO_PATH = "/Users/james/Desktop/DEMO_J.XPT"

HEI2015_NHANES_FPED(FPED_PATH, NUTRIENT_PATH, DEMO_PATH)

#Use the example data
data("NHANES_20172018")
HEI2015_NHANES_FPED(NHANES_20172018$FPED, NHANES_20172018$NUTRIENT, NHANES_20172018$DEMO)
```

#### Calculating AHEI for NHANES_FPED
```
FPED_PATH = "/Users/james/Desktop/fped_dr1tot_1718.sas7bdat"
NUTRIENT_PATH = "/Users/james/Desktop/DR1TOT_J.XPT"
DEMO_PATH = "/Users/james/Desktop/DEMO_J.XPT"

AHEI_NHANES_FPED(FPED_PATH, NUTRIENT_PATH, DEMO_PATH)

#Use the example data
data("NHANES_20172018")
AHEI_NHANES_FPED(NHANES_20172018$FPED, NHANES_20172018$NUTRIENT, NHANES_20172018$DEMO)
```

#### Calculating DASH for NHANES_FPED
```
FPED_PATH = "/Users/james/Desktop/data/fpre_dr1tot_1718.sas7bdat"
NUTRIENT_PATH = "/Users/james/Desktop/data/DR1TOT_J.XPT"
DEMO_PATH = "/Users/james/Desktop/data/DEMO_J.XPT"
DBQ_PATH = "/Users/james/Desktop/data/DBQ_J.XPT"

DASH_NHANES_FPED(FPED_PATH, NUTRIENT_PATH, DEMO_PATH, DBQ_PATH)

#Use the example data
data("NHANES_20172018")
DASH_NHANES_FPED(NHANES_20172018$FPED, NHANES_20172018$NUTRIENT, NHANES_20172018$DEMO, NHANES_20172018$DBQ)

```

#### Calculating MED for NHANES_FPED
```
FPED_PATH = "/Users/james/Desktop/fped_dr1tot_1718.sas7bdat"
NUTRIENT_PATH = "/Users/james/Desktop/DR1TOT_J.XPT"
DEMO_PATH = "/Users/james/Desktop/DEMO_J.XPT"

MED_NHANES_FPED(FPED_PATH, NUTRIENT_PATH, DEMO_PATH)

#Use the example data
data("NHANES_20172018")
MED_NHANES_FPED(NHANES_20172018$FPED, NHANES_20172018$NUTRIENT, NHANES_20172018$DEMO)

```

#### Calculating AHEI for BLOCK
```
DATA_PATH <- "/Users/james/Desktop/data.csv"
RAW_DATA <- read_csv(DATA_PATH)

AHEI_BLOCK = AHEI_SERV(RAW_DATA)
```

#### Calculating HEI2015 for your own dietary assessment tool
```
DATA_PATH <- "/Users/james/Desktop/data.csv"
SERV_DATA <- read_csv(DATA_PATH)

HEI2015(SERV_DATA, SERV_DATA$RESPONDENTID, SERV_DATA$TOTALKCAL, SERV_DATA$VEG_SERV, SERV_DATA$FRT_SERV, SERV_DATA$WGRAIN_SERV, SERV_DATA$NUTSLEG_SERV, SERV_DATA$N3FAT_SERV, SERV_DATA$PUFA_SERV, SERV_DATA$SSB_FRTJ_SERV, SERV_DATA$REDPROC_MEAT_SERV, SERV_DATA$TRANS_SERV, SERV_DATA$SODIUM_SERV, SERV_DATA$ALCOHOL_SERV)

#Use the example data
data("SERV_DATA_exp")
HEI2015(SERV_DATA_exp, SERV_DATA_exp$UserName, SERV_DATA_exp$TOTALKCAL, SERV_DATA_exp$TOTALFRT_SERV_HEI2015, SERV_DATA_exp$FRT_SERV_HEI2015, SERV_DATA_exp$VEG_SERV_HEI2015, SERV_DATA_exp$GREENNBEAN_SERV_HEI2015, SERV_DATA_exp$TOTALPRO_SERV_HEI2015,  SERV_DATA_exp$SEAPLANTPRO_SERV_HEI2015, SERV_DATA_exp$WHOLEGRAIN_SERV_HEI2015, SERV_DATA_exp$DAIRY_SERV_HEI2015, SERV_DATA_exp$FATTYACID_SERV_HEI2015, SERV_DATA_exp$REFINEDGRAIN_SERV_HEI2015,  SERV_DATA_exp$SODIUM_SERV_HEI2015, SERV_DATA_exp$ADDEDSUGAR_SERV_HEI2015, SERV_DATA_exp$SATFAT_SERV_HEI2015)

```

#### Calculating AHEI for your own dietary assessment tool
```
DATA_PATH <- "/Users/james/Desktop/data.csv"
SERV_DATA <- read_csv(DATA_PATH)

AHEI(SERV_DATA, SERV_DATA$RESPONDENTID, SERV_DATA$GENDER, SERV_DATA$VEG_SERV, SERV_DATA$FRT_SERV, SERV_DATA$WGRAIN_SERV, SERV_DATA$NUTSLEG_SERV, SERV_DATA$N3FAT_SERV, SERV_DATA$PUFA_SERV, SERV_DATA$SSB_FRTJ_SERV, SERV_DATA$REDPROC_MEAT_SERV, SERV_DATA$TRANS_SERV,SODIUM_SERV, SERV_DATA$ALCOHOL_SERV)

#Use the example data
data("SERV_DATA_exp")
AHEI(SERV_DATA_exp, SERV_DATA_exp$UserName, SERV_DATA_exp$SEX, SERV_DATA_exp$VEG_SERV_AHEI, SERV_DATA_exp$FRT_SERV_AHEI, SERV_DATA_exp$WGRAIN_SERV_AHEI, SERV_DATA_exp$NUTSLEG_SERV_AHEI, SERV_DATA_exp$N3FAT_SERV_AHEI, SERV_DATA_exp$PUFA_SERV_AHEI, SERV_DATA_exp$SSB_FRTJ_SERV_AHEI, SERV_DATA_exp$REDPROC_MEAT_SERV_AHEI, SERV_DATA_exp$TRANS_SERV_AHEI, SERV_DATA_exp$SODIUM_SERV_AHEI, SERV_DATA_exp$ALCOHOL_SERV_AHEI)

```

#### Calculating DASH for your own dietary assessment tool
```
DATA_PATH <- "/Users/james/Desktop/data.csv"
SERV_DATA <- read_csv(DATA_PATH)

DASH(SERV_DATA, SERV_DATA$RESPONDENTID, SERV_DATA$FRT_FRTJ_SERV, SERV_DATA$VEG_SERV, SERV_DATA$NUTSLEG_SERV, SERV_DATA$WGRAIN_SERV, SERV_DATA$LOWF_DAIRY_SERV, SERV_DATA$SODIUM_SERV, SERV_DATA$REDPROC_MEAT_SERV, SERV_DATA$SSB_FRTJ_SERV)

#Use the example data
data("SERV_DATA_exp")
DASH(SERV_DATA_exp, SERV_DATA_exp$UserName, SERV_DATA_exp$FRT_FRTJ_SERV_DASH, SERV_DATA_exp$VEG_SERV_DASH, SERV_DATA_exp$NUTSLEG_SERV_DASH, SERV_DATA_exp$WGRAIN_SERV_DASH, SERV_DATA_exp$LOWF_DAIRY_SERV_DASH, SERV_DATA_exp$SODIUM_SERV_DASH, SERV_DATA_exp$REDPROC_MEAT_SERV_DASH, SERV_DATA_exp$SSB_FRTJ_SERV_DASH)

```

#### Calculating MED for your own dietary assessment tool
```
DATA_PATH <- "/Users/james/Desktop/data.csv"
SERV_DATA <- read_csv(DATA_PATH)

MED(SERV_DATA, SERV_DATA$RESPONDENTID, SERV_DATA$FRT_FRTJ_SERV, SERV_DATA$VEG_SERV, SERV_DATA$WGRAIN_SERV, SERV_DATA$LEGUMES_SERV, SERV_DATA$NUTS_SERV,FISH_SERV, SERV_DATA$REDPROC_MEAT_SERV, SERV_DATA$MONSATFAT_SERV, SERV_DATA$ALCOHOL_SERV)

#Use the example data
data("SERV_DATA_exp")
MED(SERV_DATA_exp, SERV_DATA_exp$UserName, SERV_DATA_exp$FRT_FRTJ_SERV_MED, SERV_DATA_exp$VEG_SERV_MED, SERV_DATA_exp$WGRAIN_SERV_MED, SERV_DATA_exp$LEGUMES_SERV_MED, SERV_DATA_exp$NUTS_SERV_MED, SERV_DATA_exp$FISH_SERV_MED, SERV_DATA_exp$REDPROC_MEAT_SERV_MED, SERV_DATA_exp$MONSATFAT_SERV_MED, SERV_DATA_exp$ALCOHOL_SERV_MED)

```

#### Calculating DII for your own dietary assessment tool
```
DATA_PATH <- "/Users/james/Desktop/data.csv"
SERV_DATA <- read_csv(DATA_PATH)

DII(SERV_DATA, SERV_DATA$RESPONDENTID, SERV_DATA$ALCOHOL, SERV_DATA$VITB12, SERV_DATA$VITB6, SERV_DATA$BETACAROTENE, SERV_DATA$CAFFEINE, SERV_DATA$CARBOHYDRATE, SERV_DATA$CHOLESTEROL, SERV_DATA$ENERGY, SERV_DATA$EUGENOL, SERV_DATA$FAT, SERV_DATA$FIBER, SERV_DATA$FOLICACID, SERV_DATA$GARLIC, SERV_DATA$GINGER, SERV_DATA$IRON, SERV_DATA$MAGNESIUM, SERV_DATA$MUFA, SERV_DATA$NIACIN, SERV_DATA$N3FATTYACID, SERV_DATA$N6FATTYACID, SERV_DATA$ONION, SERV_DATA$PROTEIN, SERV_DATA$PUFA, SERV_DATA$RIBOFLAVIN, SERV_DATA$SAFFRON, SERV_DATA$SATFAT, SERV_DATA$SELENIUM, SERV_DATA$THIAMIN, SERV_DATA$TRANSFAT, SERV_DATA$TURMERIC, SERV_DATA$VITA, SERV_DATA$VITC, SERV_DATA$VITD, SERV_DATA$VITE, SERV_DATA$ZINC, SERV_DATA$TEA, SERV_DATA$FLAVAN3OL, SERV_DATA$FLAVONES, SERV_DATA$FLAVONOLS, SERV_DATA$FLAVONONES, SERV_DATA$ANTHOCYANIDINS, SERV_DATA$ISOFLAVONES, SERV_DATA$PEPPER, SERV_DATA$THYME, SERV_DATA$ROSEMARY)

#Use the example data
data("DHQ3_exp")
DII(DHQ3_exp, DHQ3_exp$`Respondent ID`, DHQ3_exp$`Alcohol (g)`, DHQ3_exp$`Vitamin B12 (mcg)`, DHQ3_exp$`Vitamin B6 (mg)`)

```

#### Add dietary index output to your own data
```
#Store the output of HEI2015 in "HEI2015_output"
HEI2015_output = HEI2015(SERV_DATA, SERV_DATA$RESPONDENTID, SERV_DATA$TOTALKCAL, SERV_DATA$VEG_SERV, SERV_DATA$FRT_SERV, SERV_DATA$WGRAIN_SERV, SERV_DATA$NUTSLEG_SERV, SERV_DATA$N3FAT_SERV, SERV_DATA$PUFA_SERV, SERV_DATA$SSB_FRTJ_SERV, SERV_DATA$REDPROC_MEAT_SERV, SERV_DATA$TRANS_SERV, SERV_DATA$SODIUM_SERV, SERV_DATA$ALCOHOL_SERV)

#Merge the HEI2015_output with your own data by the participant ID
#Here, the participant ID is "RESPONDENTID", but the actual name depends on your data and it should be the column name of SERV_DATA$RESPONDENTID in the HEI2015 function
merge(yourdata, HEI2015_output, by="RESPONDENTID")
```



### Related Work
___

**dietaryindex** is mainly intended as a versatile tool to help for calculating different dietary indexes conveniently. It is designed to be flexible to work for almost all types of dietary assessment tools, including food frequency questionnaires, 24-hours dietary recalls, and even food records, while itself supports many 1-step dietary index calculations for NHANES, ASA24, DHQ3, BLOCK, and AARP.  Please follow the instruction of your specific dietary assessment tools and relevant articles regarding how to accurately define the serving size (see above) if it is not provided in our package, as they are the key to obtain high-quality dietary indexes. **dietaryindex** also provides some help in defining the serving size in the help file, argument section. Note: some very specific dietary index components (low-fat dairy) are difficult to assess, so the author(s) used his best judgment to estimate those components based on the other existing data, such as the Per capita consumption of low fat cottage cheese in the United States from 2000 to 2020 and the proportion of low-fat milk consumption in the NHANES data. Please use your own judgment to determine if the dietary indexes calculated using the **dietaryindex** package is appropriate for your research.

This package requires the **dplyr**, **readr**, and **haven** packages to be installed. Library statements of the dplyr, readr, and haven packages are included for your convenience. 

For NHANES data:
FPED file refers to the DR1TOT file in the Food Patterns equivalents for foods in the WWEIA (https://www.ars.usda.gov/northeast-area/beltsville-md-bhnrc/beltsville-human-nutrition-research-center/food-surveys-research-group/docs/fped-databases/). This is a zip file, so please unzip this file first to retrieve the SAS file. 

NUTRIENT file refers to the DR1TOT file in the Dietary Interview - Total Nutrient Intakes, First Day, Dietary Data (example: 05-06 https://wwwn.cdc.gov/nchs/nhanes/search/datapage.aspx?Component=Dietary&CycleBeginYear=2005). 

DEMO file refers to the DEMO file in the Demographic Variables & Sample Weights (example: 05-06 https://wwwn.cdc.gov/nchs/nhanes/search/datapage.aspx?Component=Demographics&CycleBeginYear=2005)

DBQ file refers to the DBQ file in the Diet Behavior & Nutrition, Questionnaire Data (example: 05-06 https://wwwn.cdc.gov/nchs/nhanes/search/datapage.aspx?Component=Questionnaire&CycleBeginYear=2005)

### Contributing

**dietaryindex** is licensed under the [MIT License]. Please check out the [Contribution guide](https://github.com/jamesjiadazhan/dietaryindex/blob/main/CONTRIBUTING.md) for questions, feature requests and bug reports. The maintainer will review pull requests and incorporate contributions at his discretion. You may also reach out to the maintainer, James Jiada Zhan, via his email: jzha832@emory.edu.
