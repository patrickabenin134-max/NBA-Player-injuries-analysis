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

This created matching issues d*ring SQL JOIN operations.

Solutio*:

- Identified affected records
-*Cleaned player names in Excel
- Re*laced original values with the cle*ned version

#### Duplicate Player*

Multiple players shared the same*name.

Solution:

Created a compos*te key:

```sql
Player_Name + NBA_*ntry_Year
```

This ensured unique*player identification throughout t*e analysis.

---

## Data Modellin*

After cleaning the data, I ident*fied the key variables required:

* Player Name
- Injury Periods
- Po*ition
- Season Statistics

The dat* was then prepared for SQL analysi*.

---

## Performance Scoring Mod*l

To compare players objectively,*I created a weighted performance s*ore.

### Methodology

1. Research*d the most important statistics fo* each NBA position.
2. Ranked thos* statistics by importance.
3. Assi*ned weights from 7 (most important* to 1 (least important).
4. Calcul*ted a weighted average score.

Thi* generated a single performance in*icator for each player.

---

## S*L Analysis

The SQL workflow follo*s two main steps.

### Step 1 - Da*a Preparation (CTEs)

Common Table*Expressions were used to:

- Prepa*e data
- Combine datasets
- Calcul*te intermediate metrics

### Step * - Final Analysis

The final query*was used to:

- Calculate player s*ores
- Analyse injury history
- Co*pare career trends

### SQL Concep*s Used

- JOINs
- CTEs
- Aggregati*ns
- CASE statements
- Data transf*rmations

---

## Power BI Dashboa*d

The SQL output was imported int* Power BI.

The dashboard includes*

- Overall player scores
- Perfor*ance evolution
- Most injured play*rs
- Least injured players
- Injur* comparisons

Custom measures were*created to improve the presentatio* and interpretation of results.

-*-

## Challenges Faced

### Data Q*ality Issues

- Incorrect column f*rmats
- Duplicate records
- Incons*stent player names

### SQL Readab*lity

The first versions of the SQ* script became difficult to mainta*n.

After discovering Common Table*Expressions (CTEs), I restructured*the code to increase readability a*d reduce duplication.

### Power B* Measures

Several visualisations *nitially produced misleading resul*s.

Custom measures were developed*to ensure accurate reporting.

---*
## Key Findings

The analysis sug*ests that:

- The most injured pla*ers are often among the highest-pe*forming players.
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
