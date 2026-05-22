# **Reports of Urban Issues in Zurich: A Spatial and Temporal Analysis**

### *Description:*

This Project analyses possible spatial and temporal pattern of Reports of Urban Issues in Zurich using open data from Zueriewieneu reporting platform and spatial boundaries of Zurichs neighborhoods.



The goal is to identify possible patterns, thats why the follwing questions are analysed and visualized:



1. Which neighborood in Zurich receives the highest amount of reports?
2. Which categories are the most common across the city of Zurich?
3. How does the number of reports vary per month? vary per year?
4. Are certain problem categories concentrated in specific neighbourhoods?
5. Does processing time differ by different categories or neighborhoods?



### *Data Source:*

*The rawdata folder is not included in this repository. Therefore the following dataset have to be downloaded first and placed into data/rawdata/data/*



1. Reports of Urban Issues in Zurich from the platform Zueriwieneu (zueriwieneu\_data.csv):
Reports from 2013 till 2026, Point Data set with originally 72606 entries and 19 data columns
Link to obatin the original Dataset:https://data.stadt-zuerich.ch/dataset/geo\_zueri\_wie\_neu/resource/eacc0a5c-5526-47e6-bdb5-c5174491744e
2. Spatial Boundaries of Zurichs Neighborhood form open Data Stadt Zurich (quartier\_data.gpkg):3 layers but the "stzh.adm\_statistische\_quartiere\_v.gpkg": Polygon Layer was used with originally 34 entries and 7 columns, CRS:2056, Link to obatin the original Dataset:https://data.stadt-zuerich.ch/dataset/geo\_statistische\_quartiere/resource/07562def-426f-4e00-87d7-3a0e831c6f93



## *Setup Instructions:*

This project was developed using Python 3.11 in a Conda environment.



To recreate the project environment, run the following command from the root folder of the repository:

1. Ensure you have conda installed
2. Run: conda env create -f environment.yml
3. Activate: conda activate project\_ri
4. Open: Jupyter Lab
5. Select: Kernel Python (project\_ri)



## *Execution Order:*

First, execute the Jupyter Notebook: "reports\_cleaning.ipynb" from top to Bottom. The output will be safed in the relative file data/proccesseddata as " zueriwieneu\_cleaned.csv"



Seconldy execute the Jupyter Notebook: "spatialjoin.ipynb" from top to Bottom. Two outputs will be genreated and safed in the relative file data/proccesseddata as "zh\_quartiere\_clean.gpkg" and "reports\_with\_quartiere.gpkg"



Lastly run the Jupyter Notebook: "analysis\_and\_visualization.ipynb" from top to Bottom. The visualisations and tables will be exported into the "output" ordner.

Important outputs are:

* a visualisation (map) of the report datapoints and the neighborhoods (polygons)
* a table and visualization (bar chart) of which neighborhood and Kreis receives the highest amount of reports
* a table, little detailed insight, and visualization(bar chart) of which category of report is most common
* a visualization (line chart) of the progress of reports per month and per year
* a frequencytable of absolut count of each cateogry in the neighborhoods
* a visualisation (map) of the dominat category in each neighborhood, but without the most dominant category "Abfall/Sammelstelle"
* a table /statistics on the progressing time of each category and neighborhood(top 5)
* a visualisation (barchart) of the progressing time of each category and neighborhood

