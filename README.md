# Transborder-Freight-Data-Analysis-Project
An analysis of transborder freight transportation patterns, trade relationships, and economic factors between the United States, Canada, and Mexico.

Tools used for the Project
I initially decided to use Goggle Colab to handle this project but the dataset was very huge and that caused my notebook to run slow or collapse anytime I was handling complex operations so I decided to also use Jupyter Notebook to handle the rest of the operations for this project.

Google Colab - I used this platform for obtaining the several CSV files from the zipped folder and mergED them into a single CSV file.

Jupyter Notebook  - I used this platform for performing exploratory data analysis, data cleaning, data visualization and preparation of presentation slides.

Dataset 
The dataset I used for my analysis was obtained from thinkific's OneDrive link. I proceeded to download the zip file and started to extract the files to work on. I used Colab notebook downloads, extracts, and combines data from multiple zip files into a single pandas DataFrame. I performed the following operations to process and analyze transportation data:
1. Split Zip files: I split the main zip file into various zip files to reduce the size and increase the runtime.
2. Data Loading: I loaded the split zip files that contained the transportation data.
3. File Merging and Extraction: The split zip files were merged into a single zip file, and then extracted.
4. Nested Zip Extraction: The main extracted zip file (data.zip) contained the nested zip files. I decided to let the notebook iterate through these nested zips and extracts their contents into a dedicated directory.
5.CSV File Identification: After extracting all nested zips, I identified all the CSV files within the extracted directories.
6.Data Loading and Combination: Each identified CSV file was loaded into a pandas DataFrame, and all individual DataFrames were concatenated into a single, comprehensive DataFrame.
7.Data Saving: The combined DataFrame was saved to a new CSV file (combined_data.csv) for easier access and future analysis.
8.Cleanup: I deleted the original split zip files, merged zip file, and intermediate extracted directories to free up space.
9. Data Loading and Assessment: I read the saved combined_data.csv file and loaded it back into a DataFrame on both Colab and Jupyter Notebook. Some of the initial data assessment I performed were targeted at looking at the shape, dtypes, head, sample, tail, describe, and info to understand the data's structure, types, and basic statistics.

There were 36,347,182 entries, 15 features (TRDTYPE, USASTATE, COMMODITY2, DISAGMOT, MEXSTATE, CANPROV, COUNTRY, VALUE, SHIPWT, FREIGHT_CHARGES, DF , CONTCODE, MONTH, YEAR and DEPE) but after assessing and cleaning my dataset there are 25,905,850 entries, 11 features in the dataset (trdtype, commodity, disagmot, country, value, shipwt, freight_charges, df, contcode, month and year). Most of the variables are categorical in nature but value, shipwt and freight_charges are numeric in nature.


Business Questions
1. What was the most used trade type used for the transborder freight?
2. Which Country had the most trade activity for the transborder freight?
3. Which merchandise was patronized for the transborder freight trade?
4. Which freight packaging method was most used in the transborder freight trade?
5. What was the most used transportation type used for the transborder freight?
6. What was the mode of transportation that was used for the various trade type?
7. What was the top 10 most patronized commodities that was transported by the various transportation mode?
8. Are there any yearly seasonal patterns in the freight costs?
9. Does the freight cost correlate with the ship weight?
10. Does freight costs correlate with ship weight and value?
11. What was the trade type utilized by the two countries?
12. How were the goods packaged for the various trade types that were utilized by the two countries?


Data Visualization
I first created 4 random sampled DataFrames each with 1000000 rows for my visualizations based on the huge size of my data.

Summary of Findings

Univarite Visualization
I first created a series of bar plots to visualize the distribution of some of the categorical variables based on my business questions.

1. Check the relation between the Trade Type (What was the most used trade type used for the transborder freight?).
From the first plot of the four sampled data I realized that Export was the most used type of trade as compared to Import. The highest count for Export from the four plots was 695,731 as compared to 304,269 for Import.

2. Check the relation between Country (Which Country had the most trade activity for the transborder freight?).
From the second plot of the four sampled data I realized that the country with the most trade activity was Canada as compared to Mexico. The highest count for Canada from the four plots was 621,269 as compared to 378,731 for Mexico.


3. Check distribution of Domestic/Foreign Code (Which merchandise was patronized for the transborder freight trade?)
From the third plot of the four sampled data I realized that the most patronized merchandise for the transborder activity was the Domestically produced merchandise as compared to the Foreign produced merchandise. The highest count for the Domestically produced merchandise from the four plots was 762,928 as compared to 237,072 for the Foreign produced merchandise.

4. Check distribution of Container Code (Which freight packaging method was most used in the transborder freight trade?)
From the fourth plot of the four sampled data I realized that the Non-containerized packaging method most patronized packaging method for the transborder activity as compared to the Containerized packaging method. The highest count for the Non-containerized from the four plots was 602,515 as compared to 397,485 for the Containerized.

5. Check the relation between the Transportation Type (What was the most used transportation type used for the transborder freight?).
From the fifth plot of the four sampled data I realized that Trucks were the most used transportation type. This was followed by Air and Rail transport. The least favored type of transport was via Mail (U.S Postal Service). The highest count for the Trucks from the four plots was 704,757 as compared to 465 for Mail (U.S Postal Service).

Bivarite Visualization
For the bivariate visualization, I investigated the relationships between pairs of variables in my data.

6. What was the mode of transportation that was used for the various trade type?
From the plot of the four sampled data I realized that for almost all the transportation type used they were used for mainly Exports as compared to the number of Imports done with the transportation type. The only exception was with the Foreign Trade Zones(FTZs) that was only used for Import and no Export.
I also realized that the use of Trucks was still the most used transportation type and they were also used for mainly Exports. This was followed by Air and Rail transport. The least favored type of transport was via Mail (U.S Postal Service). The highest count for the Trucks from the four plots was 502,772 for Export as compared to 201,985 for Import.

7.What was the top 10 most patronized commodities that was transported by the various transportation mode?
The top 10 commodities that were transported by trucks are listed below;
(1). 84 - Nuclear reactors, boilers, machinery and mechanical appliances; parts thereof
(2). 85 - Electrical machinery and equipment and parts thereof; Sound recorders and reproducers, television image and sound recorders and reproducers, and parts and accessories of such articles
(3). 39 - Plastics and articles thereof
(4). 87 - Vehicles, other than railway or tramway rolling stock, and parts and accessories thereof
(5). 90 - Optical, photographic, cinematographic, measuring, checking, precision, medical or surgical instruments and apparatus; Parts and accessories thereof
(6). 73 - Articles of iron or steel
(7). 40 - Rubber and articles thereof
(8). 94 - Furniture; Bedding, mattress supports, cushions and similar stuffed furnishings; Lamps and lighting fittings, not elsewhere specified or included; Illuminated signs, illuminated nameplates and the like; Prefabricated buildings
(9). 38 - Miscellaneous chemical products
(10). 48 - Paper and paperboard; Articles of paper pulp, of paper or of paperboard

8. Are there any yearly seasonal patterns in the freight costs?
From the line plot of the four sampled data I realized that the general trend for Sample 1, 2 and 3 was that the mean freight charges increases from 2020, then hits a peak mean freight charge in 2022 and then drops from 2023 and then further drops in 2024 with the exception of the fourth sampled plot. For the fourth sampled plot I observed that the Mean Freight Charges increased from 2020 to 2021 and then increased again from 2021 to 2022 but did not hit a peak in that year as compared to the other 3 sampled plots. From 2022 the charges dropped in 2023 but then the charge for that sample defied the norm of further dropping in 2024 to rising to its peak.
The 3rd sample plot also had a deviation from the because it was the only incident where the mean freight charge for 2024 was lower than the starting mean freight charge for 2020.
This is a clear indication that the freight charges need to be reviewed to assure the business makes profit. 

9. Does the freight cost correlate with the ship weight?
From the scatter plot of the four sampled data I realized that most of the points were mostly clustered quite close to the origin which could mean that there may be a weak correlation between the freight charges and the ship weight which means it has to be studied further.

10. Does freight costs correlate with ship weight and value?
From the Correlation heatmap plot of the four sampled data I realized that there is a strong positive correlation between ship weight and freight charges with a moderate positive between the ship weight and value and also a moderate positive correlation between freight charges and value.

11. What was the trade type utilized by the two countries?
From the plot of the four sampled data I realized that for the two countries the most used trade type was Exports as compared to the number of Imports done by the two countries. 
The highest count for Canada from the four plots was 385,169 for Export as compared to 236,100 for Import.
The highest count for Mexico from the four plots was 311,431 for Export as compared to 68,603 for Import.

12. How were the goods packaged for the various trade types that were utilized by the two countries?
From the plot I observed that the goods exported to Canada were all containerized while the goods imported to Canada were all Non-containerized. The highest count of goods that were exported to Canada and containerized was 385,169. The highest count of goods that were imported to Canada and non-containerized was 236,616.
I also observed that the goods exported to Mexico were mainly containerized with a few being non-containerized while the goods imported to Mexico were all Non-containerized.
The highest count of goods that were exported to Mexico and containerized was 296,774 and the highest count of goods that were exported to Mexico and non-containerized was 13,840. The highest count of goods that were imported to Mexico and non-containerized was 68,705.
