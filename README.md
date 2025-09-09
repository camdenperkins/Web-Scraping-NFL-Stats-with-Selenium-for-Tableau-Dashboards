# Web-Scraping-NFL-Stats-with-Selenium-for-Tableau-Dashboards
Independent Project by Camden Perkins

# Introduction
With the recent completion of Week 1 of the 2025–26 NFL season, I decided to build a project that reflects both my passion for football and my interest in analytics. 
To gather the data, I used web scraping techniques such as Selenium in Python to extract game scores and outcomes directly from [Pro Football Reference](https://www.pro-football-reference.com/). Selenium allowed me to dynamically navigate and collect structured data from the site, which I then cleaned and enriched using pandas.
Once the data was prepped, I visualized it in Tableau to showcase my capabilities with interactive dashboards, calculated fields, and custom labeling. The final product highlights position-based performance and team-level comparisons, showcasing how player roles and team dynamics shaped outcomes across the week’s matchups.
This project not only demonstrates my technical proficiency in Python and Tableau, but also my ability to build end-to-end pipelines that automate tedious tasks and deliver actionable insights.

# Web Scraping with Selenium

To collect player-level offensive stats from Week 1 NFL matchups, I built a scraping function using Selenium in Python. This allowed me to automate browser navigation and extract the offense tables from each game’s box score page on Pro Football Reference.

The scrape_game() function launches a headless Chrome browser, loads the game page, and locates the offense table embedded inside an HTML comment block. I then parse the table using pandas.read_html() and return it as a DataFrame.

<img width="524" height="178" alt="image" src="https://github.com/user-attachments/assets/51dcec50-6843-4fbe-9705-0304758df34c" />

# Data Cleaning with Pandas

After scraping, I cleaned and standardized the data using a custom clean_offense_table() function. This step flattens multi-level column headers, removes repeated header rows, and renames columns to follow a consistent naming convention (e.g., pass_yds, rush_att, rec_tds).

<img width="536" height="188" alt="image" src="https://github.com/user-attachments/assets/7796be55-0032-4806-b96d-f818ffbb1b02" />

# Aggregating and Structuring the Dataset
I then looped through a list of game URLs from Week 1, scraped and cleaned each game’s offense table, and stored the results in a dictionary keyed by matchup. Finally, I concatenated all games into a single DataFrame, all_games_df, for analysis and visualization. I saved this dataset locally so I could easily import it into Tableau for dashboard creation.

<img width="491" height="247" alt="image" src="https://github.com/user-attachments/assets/5735d053-15b4-4415-83fd-e0270b645885" />

# Tableau
### Running Back Performance Analysis

### Team Passing Yards Comparison
