# University_Admission_Modelling
### Contact information
Author: Reema Sipra
Email: siprar.jacobs@gmail.com

## Table of contents

1. [Introduction](#introduction)
2. [Project Objectives](#project-objectives)
3. [High level methodology](#highlevel-methodology)
4. [Data source](#data-source)
5. [Dataset](#data-dictionary)
6. [Environment](#environment)
7. [Project Structure](#project-structure)
8. [Notebooks](#notebooks)
9. [Installation and Usage](#installation-and-usage)

## Introduction 

One of the biggest decision points for students and their parents is picking a suitable university and career. People spend considerable resources to pick and get into the right university. With increasing educational costs and facing an increasingly competitive job market after graduation, making an informed decision is even more crtical for prospective students and their families.

The key to making an informed decision is relevant data that is presented in a useful manner. There is a wealth of information provided by govrenmental institutions and universities that can be analyzed through machine learning models to support such desicion making. Leveraging techniques such as time series analysis through AutoRegressive (AR) models and Convolutional Neural Networks (CNN), this project aims to provide a nuanced understanding of the complex interplay between these variables and future financial success.

Furthermore, these models have the potential to also support university with their strategies by enabling them to tailor their programs to better align with the financial expectations of students and enhance overall educational outcomes. It can also support diversification of the student body.

## Project Objectives:
The objectives of the project have been updated to the following since Sprint-1:

1. Support decision making of high school students & parents.
2. Create a reliable model for students to estimate earnings for given program and university.

### Highlevel methodology: 
Classification models will be developed to predict the median earnings of graduates 10 years after their entry into the University. Models considered are Logistic Regression, Random Forest, and neural networks.

## Data source: 
US Department of Education, College Scorecard (https://collegescorecard.ed.gov/data/)

**College Scorecard[here](#https://collegescorecard.ed.gov/data/documentation/):** An online tool created by the US government to allow users to compare the cost and value of higher institutional learning. Includes data on Title IV Universities (receive federal funding to make tuition affordable).
Initiated by President Obama to: " be able to see how much each school's graduates earn, how much debt they graduate with, and what percentage of a school's students can pay back their loans." 

**Three main components:** 
 - Institutional level data: (6543 universities, 15 categories, 3232 columns) over 26 years.
 - Fields of study at the universities (233,979 study areas, 160 columns) over 6 years.
 - Crosswalks:  map of differing institutional data defintion between university and the federal government (25004 records, 21 columns) over 20 years.

## Data Dictionary:
The dataset provided by College Score contains a wealth and abundance of well documented information of more than 6000 universities with 3000 columns. The following resources utilized together provide a good understanding of the dataset:

- A detailed glossary of terms can be found here [here](https://surveys.nces.ed.gov/ipeds/public/glossary).
- An excel file of the full dataset dictonary can be found [here](#https://collegescorecard.ed.gov/data/documentation/).
- A general dataframe data dictionary is included in Notebook1, titled: "01-Initial_Data_Exploration"

Some of the **key parameters** we can have a look to predict the future earnings in the dataframe prepared for analysis are: 
- University id, ('UNITID')
- Universtiy name, ('INSTNM')
- Year ('Year')
- Location (latitude / longitude), ('LONGITUDE','LATITUDE')
- Region - the US states are divided into 10 regions ('REGION')
- Type of institution (Public, Private non-profit, Private for-profit), ('CONTROL')
- Highest degree awarded by institution ('HIGHDEG')
- Number of students, ('NUM4_PUB','NUM4_PRIV','NUM4_PROG')
- Enrollment of undergraduate certificate/degree-seeking students, ('UGDS')
- Enrollment of all undergraduate students, ('UG')
- Admission rate, ('ADM_RATE') 
- Average SAT equivalent score of students admitted, ('SAT_AVG') 
- 25th percentile of SAT scores at the institution (critical reading, math, writing), ('SATVR25','SATMT25','SATWR25')
- 75th percentile of SAT scores at the institution (critical reading, math, writing), ('SATVR75','SATMT75','SATWR75')
- Midpoint of SAT scores at the institution (critical reading, math, writing), ('SATVRMID','SATMTMID','SATWRMID')
- 25th percentile of ACT scores at the institution (cumulative, english, math, writing), ('ACTCM25','ACTEN25','ACTMT25','ACTWR25')
- 75th percentile of ACT scores at the institution (cumulative, english, math, writing), ('ACTCM75','ACTEN75','ACTMT75','ACTWR75')
- Midpoint of ACT scores at the institution (cumulative, english, math, writing), ('ACTCMMID','ACTENMID','ACTMTMID','ACTWRMID')
- Percentage of degrees awarded by program ( 'PCIP01,'PCIP03','PCIP04','PCIP05','PCIP09','PCIP10','PCIP11','PCIP12','PCIP13','PCIP14','PCIP15','PCIP16','PCIP19','PCIP22','PCIP23','PCIP24','PCIP25','PCIP26','PCIP27','PCIP29','PCIP30','PCIP31','PCIP38','PCIP39','PCIP40','PCIP41','PCIP42','PCIP43','PCIP44','PCIP45','PCIP46','PCIP47','PCIP48','PCIP49','PCIP50','PCIP51','PCIP52','PCIP54')
- Tuition / price, ('NPT4_PUB', 'NPT4_PRIV', 'NPT4_PROG') 
- Percentage of undergraduates who receive a Pell Grant, ('PCTPELL') 
- Percent of all undergraduate students receiving a federal student loan, ('PCTFLOAN')
- The median debt for students who have completed, ('GRAD_DEBT_MDN')
- The median debt for Pell students, ('PELL_DEBT_MDN')
- Share of students who received a federal loan while in school, ('LOAN_EVER')
- Share of students who received a Pell Grant while in school, ('PELL_EVER')
- Number of students not working and not enrolled 10 years after entry ('COUNT_NWNE_P10')
- Number of students working and not enrolled 10 years after entry('COUNT_WNE_P10')

The **target variables** are:
- Potential earnings 10 years after entry to university, distribution. (mean, median, 10, 25, 75, 90 percentile, standard deviation), ('MN_EARN_WNE_P10','MD_EARN_WNE_P10','PCT10_EARN_WNE_P10','PCT25_EARN_WNE_P10','PCT75_EARN_WNE_P10','PCT90_EARN_WNE_P10','SD_EARN_WNE_P10').

<b>Notes</b>:
- `Column_id` is given in brackets.

## Environment
This project utilizes the "RIS_capstone_env" environment package created specifically for this project.

## Project Structure

<b>Data</b>: Contains the dataset used for analysis (or a link to the source).</br>
<b>Notebooks</b>: Jupyter notebooks document the data analysis and modeling process.</br>
<b>Reports</b>: Project reports, findings, and visualizations.</br>
<b>References</b>: Additional project documentation and resources.</br>
<b>Models</b>: All the models made.</br>
<b>Docs</b>: Additional documents required for the project.</br>

## Notebooks

<b>Notebook1:</b>: "01-Initial_Data_Exploration.ipynb". Initial examination, understanding, and extraction of relevant information from the raw csv files.
<b>Notebook2:</b>: "02- Cleaning.ipynb". Create the main dataframe for analysis by merging, filtering, and cleaning the original dataset.
<b>Notebook3:</b>: "03-Basline_LogReg_Option0.ipynb". Baseline model, logistic regression, with no imputation for NaNs in the Target column.
<b>Notebook4:</b>: "04-LogRegOption2_RandomForest.ipynb". Update Baseline model with Random Forest imputation for the NaNs in the Target Column. Advanced modelling with Random Forests. Model evaluations and Interpretation.

## Installation and Usage
To use this project, follow these steps:
<ul>
<li>

Clone the repository: 
~~~bash  
  git clone https://github.com/RSipra/University_Admission_Modelling
~~~

</li>
<li>Set up the notebook environment with the required packages. You can find the list in the requirements.txt file in the Docs directory.</li>
<li>Download the dataset from the link provided <a href= "https://drive.google.com/drive/folders/11JXs-Hqqi1mV1ttmEYA4wOl9peQwnCSu?usp=sharing"_blank">here</a>.</li>
<li>Run the Jupyter Notebooks "Notebooks" directory.</li>
</ul>
