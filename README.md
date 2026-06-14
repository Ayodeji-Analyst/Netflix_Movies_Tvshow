# Netflix_Movies_Tvshow
🎬 Netflix Movies &amp; TV Show Trend and Performance Analysis
📌 Project Overview
This project explores the Netflix content library to uncover trends in content type, ratings, genres, country of origin, and how Netflix’s catalog has evolved over time. The final output is an interactive dashboard built in Power BI that allows filtering by Movies and TV Shows.
Key metrics at a glance:
	•	8,807 total titles in the dataset
	•	TV-MA is the most common content rating
	•	Movies dominate the catalog over TV Shows
	•	United States is the top content-producing country
	•	2019 was Netflix’s peak year for content additions.

  🧹 Data Cleaning Process
The raw dataset required several cleaning steps before analysis could begin:
1. Handling Missing Values
	•	Columns with a high percentage of nulls (e.g., director, cast) were retained but flagged — missing values were replaced with "Unknown" or "Not Listed" to avoid dropping rows unnecessarily.
	•	Rows missing critical fields like title, type, or date_added were removed entirely.
2. Date Formatting
	•	The date_added column was stored as a raw string (e.g., "January 1, 2020"). It was parsed and converted to a proper date format (YYYY-MM-DD).
	•	A year_added column was extracted to support the content trend over time analysis.
3. Splitting Multi-Value Columns
	•	The listed_in (genres) and country columns contained multiple comma-separated values in a single cell.
	•	These were split and exploded into individual rows to allow accurate counting per genre and per country.
4. Standardizing Text Fields
	•	Inconsistent casing and whitespace in rating, type, and country fields were standardized using strip() and title() transformations.
	•	Entries like "TV-MA " (trailing space) were normalized to "TV-MA".
5. Filtering Outliers
	•	A small number of records had duration values in incorrect formats (e.g., minutes listed for TV shows). These were separated and handled by content type.
	•	Entries with unrealistic release_year values were reviewed and removed.
6. Creating New Columns
	•	content_type: derived from the existing type column to distinguish Movies vs. TV Shows.
	•	year_added: extracted from date_added for time-series trend analysis.
	•	primary_country: extracted the first listed country for simplified country-level analysis.

🛠️ Tools & Technologies
	•	Excel for Data cleaning and transformation
	•	Power BI for Dashboard design and visualization
	•	Dataset Source, was gotten Netflix Titles Dataset on Kaggle

  💡 Key Insights
	•	Netflix added the most content in 2019, after which additions declined — likely reflecting the impact of COVID-19 production delays and strategic catalog curation.
	•	Documentaries are by far the most common genre, followed by Comedy/Drama combos and Kids’ TV.
	•	The majority of Netflix content is rated TV-MA, suggesting the platform skews toward adult audiences.
	•	The United States and India are the two dominant content-producing countries, with India showing rapid growth in recent years.
	•	Movies make up roughly 70% of the total catalog, with TV Shows accounting for the remaining 30%.
