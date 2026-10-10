# Experimental evolution of *Chlamydomonas reinhardtii* in fluctuating versus constant temperature stress

## General File Layout
- This repo is broken down into two folders: 1) Temperature_Screen and 2) Temperature_Evolution, in accordance with phase 1 and phase 2 of the research article.

### Temperature_Evolution
 - Analysis:  Contains the main R notebook with the main analyses and functions that are used and reported in the research article. The first cell of each notebook will have the packages that are required
  - The Data_Processing folder contains a Cleaned_Data folder, which contains a parsed and cleaned version of the Raw_Data files, sorted by which Fitness Assay (FA) it is sourced from. The AUC.ipynb notebook then uses the csv files within the folder to calculate the area under the growth curves of each of the FAx.csv files to create HE_area_Table_additive.csv

### Temperature_Screen
 - Analysis:  Contains the main R notebook with the main analyses and functions that are used and reported in the research article. The first cell of each notebook will have the packages that are required. This notebook will output a bootstrapped model for each cell line used, which can be found in ./Data/Boostrapped_Models. The cell to generate these files has been turned into raw cell type to avoid overwriting these files. It will also generate ./Topt_ranges.txt which is the table containing the thermal optima ranges for each cell line.
  - The Data folder contains:
    -  Boostrapped_Models: Contains the bootstrapped models for each cell line used, generated from Temperature_Screen_Analysis.ipynb
    -  Data_Processing:
        -  Cleaned_Data: Contains a parsed and cleaned version of the Raw_Data files, sorted by which batch it is sourced from. The Combine_Data.ipynb notebook then uses the csv files within the folder to calculate the area under the growth curves of each of the cell lines to create ../Annotating/Raw_Temperature_Screen.csv
        -  Annotating: Contains the Add_Details.ipynb, which adds the semantic details of the experiment to the raw data in Raw_Temperature_Screen.csv, to produce Parsed_Temperature_Screen.csv
