# Digital Twin Definitions

## Overview
This repository contains the code and materials for an NLP (Natural Language Processing) literature review paper focusing on digital twin definitions. The paper aims to analyze and summarize existing definitions of digital twins from academic literature using NLP techniques.

## Useful links
Make sure to have the corresponding permissions to get access to the data and other docuemnts.
- Dataset : [Google Drive link](https://drive.google.com/drive/folders/1j3ldqVtpI4U4vR2CZ4huPEO7L7_YIg8K?usp=sharing)
- Overleaf file : [Overleaf link](https://www.overleaf.com/3826434843ntmvssgvsmch#878dda)
- Trello card : [Trello Card](https://trello.com/c/VR2tBggT)
- GitHub repository : [GitHub repository](https://github.com/ualsg/dt-definitions)

## Contents
- `notebooks/`: Contains the .
- `csv/`: Contains datasets or raw data used in the analysis.
- `data/`: gitignored here -- you can find the data on [Google Drive](https://drive.google.com/drive/folders/1j3ldqVtpI4U4vR2CZ4huPEO7L7_YIg8K?usp=sharing)
- `full_texts/`: gitignored here -- you can find the data on [Google Drive](https://drive.google.com/drive/folders/1j3ldqVtpI4U4vR2CZ4huPEO7L7_YIg8K?usp=sharing)
- `notebooks`: All Jupyter notebooks, numbered based on the step order. 


## Requirements
- Jupyter Notebook
- Required Python packages (specified in `requirements.txt`)

## Setup
1. Clone the repository:
   ```bash
   git clone https://github.com/ualsg/dt-definitions.git
   cd dt-definitions
   ```
2. Create a new environemnt and activate it
    ```bash
    Python -m virtualenv .venv
    source ./.venv/bin/activate
    ```
3. Install the required modules
    ```bash
    pip install -r requirements.txt
    ```



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

4. **Final Paper:**
   - **Step 6**:  Compile the findings into the final paper.

## Contributing
- Pull requests and contributions are welcome. For major changes, please open an issue first to discuss the proposed changes.

## License
This project is licensed under the [MIT License](LICENSE).

## Contact
For any questions or inquiries, please contact
- Email :  [Mahmoud (mahmoudA@nus.edu.sg)](mailto:mahmoudA@nus.edu.sg) 
- Website : [mahmoud.work](www.mahmoud.work)