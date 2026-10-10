# NBA Injury Impact Analysis

## Project Overview

This project investigates whether injuries significantly affect NBA players' performance throughout their careers.

Using historical NBA statistics and injury records from Kaggle, I analysed player performance before and after injuries to determine whether injuries generally lead to a long-term decline in performance.

---

## Research Question

Do NBA players experience a significant decrease in performance after sustaining injuries?

---

## Datasets

The project combines three Kaggle datasets:

- Player Data
- NBA Injury Data
- Season Statistics

These datasets were merged to create a unified view of player careers, injuries, and performance.

---

## Tools Used

- Excel
- SQL
- Power BI

---

## Data Preparation

### Issues Encountered

#### Height Format

The height column was incorrectly imported as a date.

To solve the issue:

- Re-downloaded the dataset
- Converted the column to text format

#### Player Name Inconsistencies

Some player names included an asterisk (*).

This created matching issues during SQL JOIN operations.

Solution:

- Identified affected records
- Cleaned player names in Excel
- Replaced original values with the cle*ned version

#### Duplicate Players

Multiple players shared the same name.

Solution:

Created a composite key:

```sql
Player_Name + NBA_*ntry_Year
```

This ensured unique*player identification throughout the analysis.

---

## Data Modelling

After cleaning the data, I identified the key variables required:

- Player Name
- Injury Periods
- Position
- Season Statistics

The data was then prepared for SQL analysis.

---

## Performance Scoring Model

To compare players objectively,I created a weighted performance score.

### Methodology

1. Researched the most important statistics for each NBA position.
2. Ranked those statistics by importance.
3. Assigned weights from 7 (most important statistics) to 1 (least important statistics).
4. Calculated a weighted average score.

This generated a single performance indicator for each player.

---

## SQL Analysis

The SQL workflow follows two main steps.

### Step 1 - Data Preparation (CTEs)

Common Table Expressions were used to:

- Prepare data
- Combine datasets
- Calculate intermediate metrics

### Step 2 - Final Analysis

The final query was used to:

- Calculate player scores
- Analyse injury history
- Compare career trends

### SQL Concepts Used

- JOINs
- CTEs
- Aggregations
- CASE statements
- Data transf*rmations

---

## Power BI Dashboard

The SQL output was imported into Power BI.

The dashboard includes

- Overall player scores
- Performance evolution
- Most injured players
- Least injured players
- Injury comparisons

Custom measures were created to improve the presentation and interpretation of results.

---

## Challenges Faced

### Data Quality Issues

- Incorrect column formats
- Duplicate records
- Inconsistent player names

### SQL Readability

The first versions of the SQL script became difficult to maintain.

After discovering Common Table Expressions (CTEs), I restructured the code to increase readability and reduce duplication.

### Power BI Measures

Several visualisations initially produced misleading results.

Custom measures were developed to ensure accurate reporting.

--- 
## Key Findings

The analysis suggests that:

- The most injured players are often among the highest-performing players.
- Modern NBA players experience more reported injuries than previous generations.
- Injuries do not appear to cause a significant long-term decline in overall career performance.

Possible explanations include:

- Improvements in sports science
- Better injury recovery methods
- Better nutrition and conditioning
- Increased availability of modern player data

---

## Limitations

- Historical injury reporting is less complete than modern records.
- Performance scoring depends on manually assigned weights.
- Some player identification issues required assumptions during the cleaning phase.

---

## What I Learned

Through this project I developed practical experience in:

- Data Cleaning
- SQL
- Relational Data Modelling
- Power BI
- Dashboard Design
- Problem Solving
- Data Validation
- Business-Oriented Analytics

---

## Future Improvements

- Introduce machine learning models
- Refine the performance scoring methodology
- Automate data cleaning processes
- Incorporate additional injury severity metrics

---

## Author

Patrick ABENIN

Master in Management - Programme Grande École  
emlyon business school
