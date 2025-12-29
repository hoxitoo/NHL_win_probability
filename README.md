ENG/RUS

# NHL_win_probability
NHL win probability model(incl.OT/SO) # Модель вероятности победы в матчах НХЛ (с учётом ОТ и буллитов)
This project is a data-drivenmodel for estimating the probability of winning NHL matches, including **overtimes and shootout**. Этот проект представляет собой аналитическую модель для оценки вероятности победы команд НХЛ, включая **овертайм и серию буллитов**.

This model uses: Модель использует:
- historical NHL data (current season + 2 previous seasons), исторические данные НХЛ (текущий сезон + 2 предыдущих),
- team strength based on **player contribution**, силу команды на основе **вклада игроков**,
- **goalie form** and expected starter logic,
- machine learning (Logistic Regressiaon).

- The output is:
- **win probability (%)**
- **fair odds** calculated as `1 / probability`

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

  
