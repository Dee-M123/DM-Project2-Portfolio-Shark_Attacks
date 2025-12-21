**Shake Attack Analysis**

The ocean has a natural ability to make a location look relaxing and aesthetically pleasing. It offers people the chance to enjoy many different water activities and sports. As lovely as it is, it is also home to many different creatures, some more dangerous than others — hence the choice of this dataset for the analysis.

Using data provided by the Global Shark Attack File
https://www.sharkattackfile.net/incidentlog.htm

this project analyses shark attack incidents from different parts of the world, with the goal of identifying patterns related to geography, human behavior, and shark species. 

**General (initial overview) assessment of the dataset:**

The dataset consists of 7058 rows and 23 columns, with an actual shape of (7058, 23). An initial inspection revealed several inconsistencies in structure and data quality. Column naming conventions were inconsistent, with a mixture of uppercase and lowercase names as well as the presence of whitespaces. 
Only the columns year and original order were classified as numeric, despite other columns such as age and date clearly containing numeric values and requiring correction.
Missing data was a significant issue in several columns. More than 99% of the values in Unnamed: 21 and Unnamed: 22 were missing, making these columns unsuitable for analysis. Approximately half of the time column contained missing values, while age and species were missing more than 40% of their entries. 
Most remaining columns had less than 8% missing data. No duplicated rows were identified; however, Case Number and Case Number.1 appeared to be duplicates, and only one was retained. The original order column, although numeric, was not analytically meaningful and was therefore removed along with the unnamed columns.
Several columns required extensive cleaning due to inconsistent or ambiguous entries. The country column contained multiple naming conventions for the same country, as well as regional names and bodies of water incorrectly listed as countries. Some entries were too vague or broad to be analytically useful. 
Similar inconsistencies were observed in the fatal_y_n and sex columns, where values were not standardized. The location column also included ambiguous entries such as combined country names or uncertain regions.

The species column required the most attention, as it contained a wide variety of descriptive, speculative, and multi-species entries. To improve analytical clarity, species names were standardized, and all unclear, speculative, or multi-species references were grouped under the label “UNKNOWN SHARK”. 
This approach allowed meaningful aggregation while preserving valid species-level information 

**Possible areas of exploration (aspects interesting to look into):**

It is said that everything that can kill you is found in Australia, it kind of has the reputation of being a playground for the “devil’s pets”, as such, one can theorise as follows: 

    H1:  Australia has the highest number of shark attacks 
    H2: Australia has the highest number of shark related deaths 

We can also use the dataset to look into American related stereotypes, they say Americans thrill chasers. Danger doesn’t really find them, but they are good at seeking it out, as such, one can hypothesis as follows: 


    H3: Americans will have the highest count of shark related attacks due to provocation. 

In line with the American thrill chasing life, men are also knowing to dive head first into danger, the following hypothesis can be built on this theory: 

    H4: Men fatality rate due to shake related attacks is higher than that of women. 

**Findings:**

    H1: American and not Australia, has the highest number of shark related attacks. 
    H2: Apparently, everything that can kill is really in Australia, it is the location with the highest number of deaths due to shark attacks. 
    H3: Of the top three countries by shark attacks, America has the highest record of shark related incidents by provocation
    H4: Men definitely find ways to live shorter lives, they have the highest record of shark related deaths.

Additionally, the analysis also found that the great white shark is the most common shark species when it comes to attacks. 

**Project Structure:** 


    ├── Data
    
    │   ├── raw_data
    
    │   └── cleaned_data
    
    ├── Notebooks
    
    │   ├── EDA1.ipynb
    
    │   ├── Cleaning2.ipynb
    
    │   └── Analytics3.ipynb
    
    ├── Reports
    
    │   ├── slides
    
    │   └── images
    
    └── README.md 

**How to Run the Project:**
1. Environment Requirements

This project was developed using:

    Python version: 3.12.12 (Google Colab)
    
    Core Libraries:
    
    - pandas
    - numpy
    - matplotlib
    - seaborn
    
These libraries are pre-installed in Google Colab, but if running locally, they must be installed manually.

**Key Insights:** 

Although the United States records the highest number of shark attacks overall, it does not have the highest fatality count. This suggests that attack frequency alone does not determine severity or outcome.
Australia shows the highest number of fatal shark attacks, indicating that encounters there are more likely to result in death. Possible contributing factors include:
- Presence of larger, more aggressive species
- Ocean conditions and distance from immediate medical assistance
- Activities such as surfing in open waters

Among the top three countries, the United States has the highest proportion of provoked shark incidents, implying that:
- Many encounters may be linked to risky or intrusive human activities
- Recreational water use and human–shark interaction are more frequent
  
Men account for the majority of shark-related deaths, which is likely explained by:
- Greater participation in high-risk activities (surfing, diving, fishing)
- Higher exposure time in shark-prone waters
- Behavioral risk-taking rather than biological vulnerability

The Great White shark emerges as the most frequently identified species involved in attacks. This is consistent with:
- Its large size and powerful bite
- Overrepresentation in regions such as Australia, South Africa, and parts of the U.S.
- Better species identification compared to smaller sharks

**Conclusion:**

Shark attack risk is not evenly distributed across geography, behavior, or demographics. While the United States experiences the most shark attacks overall, Australia presents a higher fatality risk, meaning that where and how humans interact with marine environments matters more than the number of encounters. 
Additionally, human behavior plays a critical role in fatal outcomes, and a small number of shark species, especially the Great White, account for the largest share of incidents.
