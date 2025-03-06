# Digital Twin Definitions

## Overview
This repository contains the code and materials for an NLP (Natural Language Processing) literature review paper focusing on digital twin definitions. The paper aims to analyze and summarize existing definitions of digital twins from academic literature using NLP techniques.


## Requirements
- Jupyter Notebook
- Required Python packages (specified in `requirements.txt`)


## Usage
1. **Data Acquisition:**
   - **Step 00**:  Download abstracts to get the uuid of each paper `./notebooks/00_elsevier_get_abstracts_mass_download.ipynb`
   - **Step 01**:  Download full text (You must acquire elsevier api institute token) `notebooks/01_elsevier_download_full_texts.ipynb`.

2. **Data Preprocessing:**
   - **Step 02**:  Organizing the data and removing duplicates `notebooks/02_oragnizing_the_data_remove_duplicates.ipynb`.
   - **Step 03**:  Using Regular Expressions (regex) to extract definitions `notebooks/03_regex_extract_definitons.ipynb`.
   - **Step 04**:  Generate embeddings using OpenAI GPT api (You must have an openAI apiKey) `notebooks/04_generate_embeddings_using_openAI.ipynb`.


3. **Exploratory Data Analysis (EDA):**
   - **Step 05**:  Generate word cloud and other EDA visuals`notebooks/05_word_cloud.ipynb`.

4. **Data Processing and Analysis:**
   - **Steps 06-17**: 
        - 06 - Extracting the industry category and sub-category from each definition `notebooks/06_extracting_dimensions.ipynb`
        - 10 - Categories' analysis `notebooks/10_analysing_categoreis.ipynb`
        - 11 - Extracting subjects from the dataset metadata `notebooks/11_extracting_subjects_for_each_paper.ipynb`
        - 12 - Extracting the most comprehensive definitions from each cluster `notebooks/12_analysing_defintions_with_LLMs.ipynb`
        - 13 - Extracting reveiw papers from the full dataset `notebooks/13_extracting_all_review_papers_using_regex.ipynb`

10. **Final Paper:**
   - **Step 6**:  Compile the findings into the final paper.


# Dataset Description: 
This is a description of the dataset:

1. #### The cleaned dataset is divided into 4 categories: 
   1. 15,000 papers where "Digital Twin" appears: 
        15,000 papers about digital twin with their metadata such as publication type, date, authors, subjects, ... etc. This dataset will be used to extract the general information about Digital Twin and funnel down to the Digital Twin in the built environment. 
        ```
        datasets
            |_ 00_clean_all_papers_details.csv
        ```
        
    2. #### Definitions: 
        800 Digital Twin definitions extracted using regular expressions (regex). Not all of them are exactly definitions but sometimes they are descriptions of digital twin or a description of a specific case. These definitions are clustered into different number of clusters to group them out based on semantic similarity. The dataset contains the original `file` name, the `title`, the `definition`, the `embedding` vector and the `cluster` of each definition. The sentence embedding vector is extracted using openAI GPT.  You can also do any number of clustering using `Kmeans` or any other model on the embedding vector if you find it might be useful to the analysis. 
        
        **Files:**
        ```
        datasets
            |_ 01_definitions_clustered_50.csv
            |_ 02_definitions_clustered_100.csv`
            |_ 03_definitions_clustered_400.csv
            |_ definitions.json 
        ```
        
        
    3. #### The Categories/subCategories of each definition paper: 
        This dataset uses the abstract to understand which industry category and subcategory does the definition belong to. 

        **Files:**
        ```
        datasets
            |_ 03_extracted_categories_and_subcategories_for_each_definition.csv
        ```
        
         
    4. #### Most comprehensive definition of each cluster: 
        This dataset contains the most representative definition of each cluster. Comprehensive in this context refers to fulfilling most components within the cluster. 
        
        **Files:**
        ```
        datasets
            |_ gpt4_most_comprehensive_definitions_5_per_cluster.json 
            |_ gpt4_most_comprehensive_definitions_5_per_cluster_v3.json
        ```

## Contact
For any questions or inquiries, please contact
- Email :  [Mahmoud (mahmoudA@nus.edu.sg)](mailto:mahmoudA@nus.edu.sg) 
- Website : [mahmoud.work](www.mahmoud.work)
