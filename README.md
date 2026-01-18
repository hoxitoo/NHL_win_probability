ENG/RUS

# NHL_win_probability
NHL win probability model(incl.OT/SO) 
This project is a data-drivenmodel for estimating the probability of winning NHL matches, including **overtimes and shootout**. 

This model uses:
- historical NHL data (current season + 2 previous seasons), 
- team strength based on **player contribution**, 
- **goalie form** and expected starter logic,
- machine learning (Logistic Regressiaon).

- The output is:
- **win probability (%)**
- **fair odds** calculated as `1 / probability`

---
## Project Goals

- predict the probability of a team's victory **before a watch**
- account for:
  - roster changes
  - team core stability
  - goalie impact
- compare model-implied adds with bookmaker liens
- build a transparent and interpretable ML pipline

---

## Data Sources

- **NHL Web API**
- schedules
- match results
- datailerd boxscore statistics (players and goalies)

Data coverage:
- current NHGL season
- two presious NHL seasons

All boxscore data is cached locally to speed up repeated runs.

  ---

## Feature Engineering

### Team Strenght (Skaters)
Calculated as the average contribution of all skaters over the last **N games**:
- goals
- assists
- shots
- hits
- blocked shots
- penalty minutes *(negative impact)*
- time on ice (TOI-weighted)

### Goalie Form
- indenfiles the **probable starting goalie**
- evalates recent perfomance using:
    - save %
    - workload (time on ice)

 ### Match Features
 - difference in skater strength (home - away)
 - difference in goalie form (home - away)

---

## Model
- **Logistic Regression**
- Target veriable:
    - home team win (included OT / shootout)
- Standardized numerical features
- - Time-aware training (no data leakage)
 
---

## Output Example

Home team win probability: 60.0%
Fair odds: 1.67

