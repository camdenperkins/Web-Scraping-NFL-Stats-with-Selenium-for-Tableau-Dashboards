# Web-Scraping-NFL-Stats-with-Selenium-for-Tableau-Dashboards
Independent Project by Camden Perkins <br>
Contact Information: 203-290-7611 / camden@fperkins.com

# Introduction
With the recent completion of Week 1 of the 2025–26 NFL season, I decided to build a project that reflects both my passion for football and my interest in analytics. 
To gather the data, I used web scraping techniques such as Selenium in Python to extract player stats and game outcomes directly from [Pro Football Reference](https://www.pro-football-reference.com/). Selenium allowed me to dynamically navigate and collect structured data from the site, which I then cleaned and enriched using pandas.
After preparing the data, I visualized it in Tableau to demonstrate my skills with interactive dashboards, calculated fields, and custom labeling. The final product highlights position-based performance showcasing how player roles and team dynamics shaped outcomes across the week’s matchups.
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
To analyze dual-threat capabilities of NFL running backs, I created a Tableau scatter plot visualizing each player's rushing versus receiving yards from Week 1. The chart focuses on the top 30 RBs by total yardage, spotlighting the most productive players. I used a Set to group standout profiles — those with high rushing, receiving, or balanced contributions — and applied a calculated field to label them cleanly: "IF [Selected RBs] THEN [Player] ELSE". This approach highlights the most impactful backs from the week, using distinct colors and dynamic labels to make them stand out visually from the rest of the dataset. <br>

<img width="356" height="341" alt="image" src="https://github.com/user-attachments/assets/55e50b2a-e7ba-4fa0-95cf-fdcbf5aaf21b" />

Notable performances include Derrick Henry, who dominated on the ground with high rushing yards but minimal receiving involvement, and Christian McCaffrey, who stood out as a true dual-threat with strong contributions in both categories. Breece Hall posted impressive rushing numbers with solid receiving support, while James Cook leaned heavily into the passing game, racking up receiving yards despite limited rushing production.

### Team Passing Yards Comparison
On a similar yet more straightforward note, I created a horizontal bar chart in Tableau to compare total passing yards among quarterbacks from Week 1. This visualization ranks each QB by yardage, making it easy to spot the top performers at a glance. A reference line marks the league average of 232 yards, helping contextualize each player's output.


<img width="641" height="346" alt="image" src="https://github.com/user-attachments/assets/5c549d31-2053-4579-9deb-30573b0d04b9" />


Josh Allen leads the pack with a commanding 394 yards, far surpassing the average and setting the tone for elite production. Justin Herbert follows with a strong 318-yard performance, while Brock Purdy and Daniel Jones each posted over 270 yards, placing them solidly above the mean. On the lower end, Jalen Hurts, Baker Mayfield, and J.J. McCarthy all fell below the average — yet notably, each of them still secured a win in Week 1, underscoring that passing volume isn’t always the deciding factor in game outcomes.

# Conclusion and Personal Note
This project showcases my ability to build a complete data pipeline—from scraping raw NFL stats with Selenium, to cleaning and structuring the data in pandas, and finally visualizing it in Tableau with calculated fields, sets, and dynamic labeling. It reflects not just technical proficiency, but also my focus on storytelling through data. Whether it's highlighting dual-threat RBs or comparing QB production, each dashboard was built to highlight meaningful insights.

Thank you for taking the time to explore this project. If you enjoyed it, I invite you to check out my other work. If you have questions, feedback, or anything else, feel free to reach out using the contact info listed above.
