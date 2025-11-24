# National Park Biodiversity Analysis

A data exploration and visualization project analyzing species and observation records collected from several U.S. National Parks. The analysis is performed in a Jupyter notebook (national-park-biodiversity-analysis.ipynb) and focuses on species categories, conservation statuses, observations per park, and endangered species patterns.

## Repository contents
- national-park-biodiversity-analysis.ipynb — Primary Jupyter notebook that contains data loading, cleaning, visualizations, and analysis.
- (data) observations.csv, species_info.csv — Dataset files (expected to be in /kaggle/input/national-parks-biodiversity-data/ when run in Kaggle). If running locally, place the CSVs in an accessible folder and update the notebook paths.

## Dataset
This project uses a National Parks Service dataset that includes:
- species_info.csv — species metadata (category, scientific_name, common_names, conservation_status)
- observations.csv — observations of species at parks (scientific_name, park_name, observations)

Note: The notebook assumes the provided dataset as-is; several conservation_status values are missing (NaN) and are handled accordingly in the analysis.

## Key analyses & visualizations
The notebook performs the following:
- Exploratory data analysis (EDA) and summary statistics for both species and observations.
- Distribution plots:
  - Species categories distribution
  - Conservation status distribution
  - Observations per park
  - Top 10 most observed species
- Combined analysis after merging datasets:
  - Heatmap of species categories across parks
  - Boxplots comparing observations by conservation status
  - Counts of endangered species by category and by park

High-level findings (from the notebook):
- Vascular plants make up a large share of recorded species.
- Many conservation_status entries are missing; when present, "Species of Concern" is common.
- There are clear differences in total observations between parks.
- A small subset of species accounts for a large number of observations.

## How to run (local / general)
1. Clone the repository:
   git clone https://github.com/suhasabhare-data/National-Park-Biodiversity-Analysis.git

2. Prepare environment (recommended):
   - Create a virtual environment (optional):
     python -m venv venv
     source venv/bin/activate  # macOS / Linux
     venv\Scripts\activate     # Windows
   - Install dependencies:
     pip install jupyter pandas numpy matplotlib seaborn

   Optionally create a `requirements.txt` with:
   pandas
   numpy
   matplotlib
   seaborn
   jupyter

   and install with:
     pip install -r requirements.txt

3. Place the dataset CSVs in a folder and update the notebook paths if necessary. In the original notebook the files are read from:
   /kaggle/input/national-parks-biodiversity-data/species_info.csv
   /kaggle/input/national-parks-biodiversity-data/observations.csv

   If running locally, either place the CSVs in the same paths or edit the cell that reads them to point to your local paths.

4. Launch the notebook:
   jupyter notebook
   and open national-park-biodiversity-analysis.ipynb, then run the cells.

## Notes & assumptions
- The notebook assumes missing conservation_status values cannot be recovered from external sources and works only with the provided data.
- Merging observations and species is performed on the `scientific_name` column; if names in the two files differ (typos, synonyms), those entries will not join.
- Plots use seaborn/matplotlib default styles; you can customize colors and figure sizes in the notebook.

## Suggestions for next steps / improvements
- Impute or enrich missing conservation_status using external taxonomic databases (e.g., IUCN, NatureServe) to improve threat analyses.
- Standardize scientific names (e.g., using accepted taxonomies) to reduce mismatches on merge.
- Add interactive visualizations (Plotly, Bokeh) for easier exploration.
- Perform temporal analysis (if observation dates are available) to investigate trends over time.
- Add automated tests or data validation checks to ensure input data quality.

## License
This repository does not include an explicit license. 


