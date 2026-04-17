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

2. **Hold 1.6**
   - Viser xG og faktiske mål pr. kamp for valgt hold/periode
   - Viser opsummering: skud, mål, total xG og gennemsnitlig xG pr. skud
   - Viser topspillere baseret på xG

3. **Spiller-sammenligning**
   - Sammenligner én reference-spiller med udvalgte ligaspillere
   - Viser nøgletal som skud, mål, total xG og mål minus xG

## Teknologier

- R
- Shiny
- dplyr
- ggplot2
- pROC
- rpart
- randomForest

## Filer i projektet

- `Opgave 1 - shiny.R`: Hovedapp (UI + server)
- `Opgave 1.4.R`: Eksempel på modeltræning og evaluering
- Datafiler indlæses fra `.RData` eller `.rds` (se afsnittet nedenfor)

## Datakrav

Appen forventer dataobjekter med følgende navne:

- `model_data`
- `Superliga_model` (eller alternativt `Brondby_model`)

Hvis objekterne ikke findes i miljøet, forsøger appen automatisk at indlæse:

- `.RData`
- `model_data.rds`
- `Brondby_model.rds`
- `Superliga_model.rds`

## Sådan kører du projektet lokalt

1. Klon repository:

```bash
git clone <repo-url>
cd "<repo-mappe>"
```

2. Installer nødvendige pakker i R:

```r
install.packages(c("shiny", "dplyr", "ggplot2", "pROC", "rpart", "randomForest"))
```

3. Sørg for, at datafiler/objekter er tilgængelige (se **Datakrav**).

4. Start appen:

```r
source("Opgave 1 - shiny.R")
```

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
