# DATA 512: Bias in Data

# Project Description

The purpose of this project is to think about bias with respect to human-centered data science. This was demonstrated by finding the distribution of the quality of articles regarding politicians from many countries using the English Wikipedia. The quality of the articles in the dataset were found using predictions from the ORES machine learning model. 

# Project Structure

Below is a tree view of how the project is structured. The data is separated into their corresponding sub-directories.

```
.
├── LICENSE
├── README.md
├── data
│   ├── data-clean
│   │   ├── population_cleaned.csv
│   │   └── wp_wpds_politicians_by_country.csv
│   ├── data-errors
│   │   ├── wp_wpds_countries-no_match.csv
│   │   └── wp_wpds_countries-no_prediction.csv
│   └── data-raw
│       ├── WPDS_2020_data\ -\ WPDS_2020_data.csv
│       └── page_data.csv
└── src
    └── hcds-a2-bias.ipynb
```

# Dataset
The data used  to create this project was gathered from two sources. One dataset was The "Politicians by Country from the English-language Wikipedia" and was obtained at [Figshare](https://figshare.com/articles/dataset/Untitled_Item/5513449). The other dataset was population data taken from the [Population Reference Bureau]. I will now briefly describe the data in each dataset.

## Politicians by Country from the English-language Wikipedia
* Page - Name of article in Wikipedia
* Country - The country that the article is associated with
* rev_id - The unique revision identification used to uniquely identify all Wikipedia articles

## Population Data
* FIPS - The country's unique [FIPS](https://en.wikipedia.org/wiki/Federal_Information_Processing_Standards) code
* Name - The name of the country
* Type - Either 'country' or 'sub-region'. Used to allow one to easily find population for an entire region
* TimeFrame - When the data for that country was gathered
* Population - The population for that country at that time frame

## Additional Data
Some additional files were created during the processing of this data that are noteworthy. The first of which is a subset of the data for which ORES could not produce a result. This data is located in the 'data/data-errors' subdirectory under the filename 'wp_wpds_countries-no_prediction.csv'.

Another dataset produced during processing was a list of countries that had no article predictions. This data is also located in the 'data/data-errors' subdirectory under the filename 'wp_wpds_countries-no_match.csv'.

# API Documentation
Scores for the articles were produced by the ORES scoring system and obtained through its corresponding [REST API](https://ores.wikimedia.org/v3/#!/scoring/get_v3_scores_context_revid_model). Documentation and further detail about the scoring can be found [here](https://www.mediawiki.org/wiki/ORES/FAQ).

# Additional Packages
* [Anaconda](https://www.anaconda.com/) was used as my data science platform. This gives you access to all the packages used in this project as well as Jupyter Notebooks which is necessary to open the single src file. The license agreement for anaconda can be found [here](https://www.anaconda.com/eula-anaconda-individual-edition).
* [Pandas](https://pandas.pydata.org/) was used extensively throughout this project as the main data manipulation tool. Pandas falls under the BSD 3-Clause License.

# Licenses
This project is licensed under the MIT License found in the root directory of this project.

The "Politicians by Country from the English-language Wikipedia" was obtained at [Figshare](https://figshare.com/articles/dataset/Untitled_Item/5513449) and posted by [Os Keyes](https://figshare.com/authors/Os_Keyes/660514). This dataset is licensed under the [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) license.

The Population dataset was obtained at the [Population Reference Bureau](https://www.prb.org/international/indicator/population/table/). I was unable to find the corresponding license for this data.
