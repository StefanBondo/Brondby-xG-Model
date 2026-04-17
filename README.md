# xG Model og Shiny Dashboard

Dette projekt estimerer sandsynligheden for, at et skud bliver til mål (xG), og viser resultaterne i en interaktiv Shiny-app.

Appen er bygget til at gøre modelresultater lette at forstå i praksis, både for hold- og spilleranalyse.

## Projektets formål

- Forudsige om et skud ender i mål baseret på kampdata
- Sammenligne flere modeller til klassifikation
- Visualisere xG, mål og spillerperformance i et brugervenligt dashboard

## Hvad appen kan

Appen indeholder tre faner:

1. **Model-sammenligning**
   - Sammenligner logistisk regression, decision tree og random forest
   - Viser `Accuracy`, `AUC` og `Brier score`
   - Viser ROC-kurver og fordeling af forudsagte sandsynligheder

## Teknologier

- R
- dplyr
- ggplot2
- pROC
- rpart
- randomForest

## Filer i projektet

- `xG - Model`:


## Hvordan xG bruges i projektet

For hvert skud beregnes en sandsynlighed mellem 0 og 1 for, om skuddet bliver til mål.

- En værdi tæt på `0` betyder lav sandsynlighed for mål
- En værdi tæt på `1` betyder høj sandsynlighed for mål

Når sandsynligheder summeres på tværs af skud, får man forventede mål (xG), som kan sammenlignes med faktiske mål.

## Mulige forbedringer

- Tilføje flere features (fx pressituation, assist-type, kampstatus)
- Hyperparameter-tuning af træbaserede modeller
- Gemme og versionere modelartefakter mere struktureret
- Deploye appen online (fx shinyapps.io)

## Forfatter

Udarbejdet som en del af eksamencase i dataanalyse.
