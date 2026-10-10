# Project Methodology

## 1. Data Preparation

I wanted to build a project around sports, so I decided to analyse the effect of injuries on NBA players.

The objective was to determine whether players experience a significant drop in performance after an injury.

To conduct the analysis, I combined three Kaggle datasets:

- Player Data
- NBA Injury Data
- Seasons Statistics

### Data Quality Issues

#### Height Column

The height column was incorrectly imported as a date.

Solution:
- Re-downloaded the dataset
- Changed the column format to text

#### Birth Dates

Birth dates were not stored consistently. Since they were not required for the analysis, no further cleaning was performed.

---

## 2. Identifying Relevant Variables

The key information used for the analysis included:

- Player name
- Injury periods
- Position
- Season statistics

To determine which statistics were most relevant, I researched the role and responsibilities of each NBA position.

---

## 3. Building Player Identifiers

During the first SQL queries, I discovered that multiple players shared the same name.

To avoid ambiguity:

- Removed duplicate records
- Created a composite key

```text
Player Name + NBA Entry Year
```

This ensured that each player could be uniquely identified.

---

## 4. SQL Analysis

After cleaning the data, I built a player-performance scoring model.

### Performance Score

The score was calculated using a weighted average based on position-specific statistics.

Methodology:

- Most important metric = Weight 7
- Least important metric = Weight 1

### SQL Structure

#### Step 1 - Data Preparation

A CTE was used to:

- Merge datasets
- Select relevant statistics
- Prepare analytical variables

#### Step 2 - Performance Analysis

The final query:

- Calculated player scores
- Counted injuries
- Compared player performance

### SQL Concepts Used

- JOINs
- Common Table Expressions (CTEs)
- Aggregations
- CASE WHEN Statements

---

## 5. Power BI Dashboard

After exporting the SQL results, I built a Power BI dashboard.

The dashboard contains:

- Overall player scores
- Career evolution
- Most injured players
- Least injured players

### Additional Challenge

Some player names contained an asterisk (*).

This prevented successful SQL joins and resulted in missing records.

Solution:

- Identified affected players
- Removed the asterisk using Excel formulas
- Replaced the original player column

---

## 6. Findings

### Key Result

The most injured players are often among the highest-performing players.

### Conclusion

The analysis suggests that injuries do not significantly affect long-term NBA player performance.

Possible explanations include:

- Better sports science
- Improved recovery methods
- Better nutrition
- Increased availability of modern player data

### Project Limitations

One limitation is that the player identifier ultimately relied on player names rather than the composite key initially designed.
