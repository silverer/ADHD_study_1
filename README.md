# Study 1: Personality Tests & ADHD

## Elisabeth R. Silver, Mikki Hebl, & Frederick L. Oswald

This code repository contains the code necessary to replicate the analyses reported by Silver et al. in their study on the implications of using personality testing in selection contexts for job applicants with ADHD. 

Some code and data files are not included in the public-facing repository. Specifically, the file `calculate_adhd_scores.R` uses Ustun and colleagues' (2017) propriety scoring algorithm for their ASRS-5 assessment of ADHD symptoms. Because it is proprietary, we do not reproduce it. Please see below for alternatives.

In addition, the data files for the sample can be provided via email request to the corresponding author (Elisabeth Silver, elisabeth.silver[@]rice.edu). The data files are not included here to protect participants' privacy. 

## Code files

1. `Study 1 cleaning and analysis.Rmd` cleans the survey data and conducts all hypothesis tests and exploratory analyses. The code produces all of the outputs reported in the paper and supplementary materials, which are stored in the `outputs/` subfolder. This script calls `calculate_adhd_scores.R`. To override issues with references to this file, see point 3 in this section. 

2. `calculate_adhd_scores.R` calculates participants' scores on the ADHD symptom severity screener using the propriety scoring algorithm developed by [Ustun and colleagues (2017)](https://doi.org/10.1001/jamapsychiatry.2017.0298). 

3. `calculate_adhd_scores_public.R` sums participants' scores on the ADHD symptom severity screener without using the proprietary algorithm. To prevent file reference issues, replace `source("calculate_adhd_scores.R")` with `source("calculate_adhd_scores_public.R")`. The results will be similar.

## Input files

1. `data/big_five_numeric_12.03.21.csv` contains the original survey data collected from Qualtrics with numeric responses to items. This is available to researchers upon request. 

2. `data/big_five_text_12.03.21.csv` contains the original survey data collected from Qualtrics with text responses to items. This is available to researchers upon request. 

3. `data/cleaned_data.csv` contains the dataset with cleaned variable names. 

4. `data/codebook.csv` maps original variable names from survey datasets to desired facet names.

5. `data/fix_reverse_code.csv` helper file to rename reverse-coded variables and transform variables accordingly.

6. `data/variable_name_list.csv` reference file for variable names.

7. `style-ref.docx` helper file to format R Markdown outputs. 

## Packages

This project uses a number of packages. Please see the code files for a complete list. One package, `statstring`, was developed by the corresponding author. To download this package, use `devtools::install_github(silverer/statstring)`. 