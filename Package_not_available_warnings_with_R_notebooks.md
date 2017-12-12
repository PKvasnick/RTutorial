# `markdown 1.6 required, but...` a podobné hlášky pri pokuse otvoriť R notebook v RStudiu

__Diagnóza__: Pravdepodobne sa vám doplietli repozitáre z ktorých R načíta balíčky, a namiesto CRAN (hoci s týmto označením) máte "snapshot" zo servera *RevolutionAnalytics*. Skúste v konzole zadať:

`> getoption("repos")`

a ak uvidíte niečo ako

`CRAN`

`"https://mran.revolutionanalytics.com/snapshot/2016-11-01"`

`CRANextra`

`"http://www.stats.ox.ac.uk/pub/RWin"`

tak máte presne tento problém.

__Náprava:__

`> options(repos = c(CRAN = "https://cran.rstudio.com", CRANextra =  "http://www.stats.ox.ac.uk/pub/RWin"))`

Po tomto nemusíte nič inštalovať, iba znova otvorte požadovaný R notebook a balíčky sa vám správne doinštalujú. 
