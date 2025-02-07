# Qlik-PLACES-Local-Health-Data

This code sample demonstrates how to build visualizations using Qlik Cloud | Analytics.  The source data for this project is "PLACES: Local Data for Better Health, County Data 2024 release" from the CDC.  It can be found [here.](https://data.cdc.gov/500-Cities-Places/PLACES-Local-Data-for-Better-Health-County-Data-20/swc5-untb/about_data)
The PLACES dataset contains model based estimates for the entire United States (fifty states in addition to the District of Columbia) for 40 measures organized into 6 categories.  Below is a breakdown of the measure count for each category:
- Health Outcomes (12)
- Disability (7)
- Health-Related Social Needs (7)
- Health Risk Behaviors (4)
- Health Status (3)
- Prevention (7)

An export of the Qlik app can be found [here.](https://github.com/clkessel/Qlik-PLACES-Local-Health-Data/blob/main/PLACES%20Health%20Data%20Qlik%20App.qvf)


Below is a snapshot of the load script.  This dataset is fairly straight forward and there were only minor changes made in the load script.  The Geolocation column contains the location data, but as the notes in the script indicate, the source data uses a format that is the opposoite of the conventional lat/long.  I added a unique identifier since one didn't exist in this data set, just in case.  Lastly, I filtered out StateDesc equal to 'United States' and 'District of Columbia'.

![load editor](https://github.com/user-attachments/assets/bbde9ad0-4717-458e-9e9d-6cecf230f4ec)

The app features a single sheet consisting of a filter pane along the top with two dimensional filters as well as several visualizations.  

The top left features a several KPI visuals, a pie chart, and a bar chart summarizing the dataset as a whole.  

The "Average Category Values for all 50 States" distribution plot shows the spread of state scores for that particular category.  The "Health Categories vs. Prevention average scores" scatter plot shows the relationship between the Prevention category score (higher is a positive indicator) and the 5 Health categories (higher is a negative indicator).  The inverse of the Prevention category scores was used, so that in general the bottom left is "better" and the top right is "worse".  Both the  the "Average Category Values for all 50 States" and "Health Categories vs. Prevention average scores" will ignore any filters selected on the sheet.  

![app sheet](https://github.com/user-attachments/assets/bf00176f-4fc0-45f7-ba7c-a5d0239d6e58)

The map visual, as well as its associated drill-down filter pane to its right, allow the user to select a category and measure and see how the states compare against one another for that particular metric.
Lastly, when a measure is selected, the title updates on the map visual, reflecting the Measure chosen.

![reactive title](https://github.com/user-attachments/assets/ac9ac9b8-1588-469a-bcec-1e53cc52a383)
