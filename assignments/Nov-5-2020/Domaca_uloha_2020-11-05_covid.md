## Domáca úloha 05/11/2020 - Covid

Predsa nemôžeme mať kurz spracovania dát bez toho, aby sme sa pozreli na dáta o Covide. 

1. Nainštalujte si balíček `COVID19`. Je to kumulovaný dátový zdroj epidemiologických dát o nákaze Sars-Cov-II vo veľkom počte krajín. 

2. Vytvoril som notebook `code/RTutorial_Covid.Rmd` v repozitári kurzu, aby ste mali aspoň prvé kroky zjednodušené.  Uvidíte, že dáta sú také aktuálne, ako pohotovo pracuje reportovanie - napríklad dnes chýbajú dáta o testoch na Slovensku za posledné dva dni. 

3. Základný prístup k dátam nie je cez tabuľku, ale cez funkciu  covid19, ktorá vyberie dáta z tabuliek požadovaných krajín (ak chcete niekoľko krajín, použite vo volaní funkcie `covid19` vektor kódov,  `country = c(“CZE”, “SVK”)`

4. Vašou úlohou je zobraziť vývoj reprodukčného čísla R. Jednoduchý odhad R, tzv. _*reprodukčné číslo Přemka Podlahy*_, sa vypočíta ako podiel týždenných súčtov nových prípadov pre aktuálny deň  a pre 5 dní späť, teda symbolicky 
   $$
   R \approx \frac{\sum_{d = dnes - 1}^{dnes-7}novozistených_d}{\sum_{d = dnes - 6}^{dnes-12}novozistených_d}
   $$
   Logika je takáto:  Priemerný človek je nákazlivý 4.8 dňa,, a sčítaním po týždňoch eliminujeme silnú týždennú periodicitu testovania. Takýto odhad koreluje s podrobným odhadom R na 98%, a jeho autorom nie je Přemek Podlaha, ale Robert Koch Institut. 

   **Návod**: Použite funkciu `dplyr::mutate` na vytvorenie nových stĺpcov. Funkcia `cumsum(x)` vracia kumulatívny súčet  vektora `x`, a funkcia `lag(x,n)` vracia vektor x posunutý o n krokov dozadu, 

   ```lag(1:5, n=1) == (NA, 1,2,3,4)```

5. Pretože vaše dáta obsahujú aj informácie o epidemických opatreniach, skúste vykresliť dáta tak, aby zobrazovali informáciu o účinku epidemických opatrení na R (napríklad voľbou `color=` v priradeniach `ggplot`-u).

**Riešenia poprosím do stredy 11. novembra vo forme `.Rmd` súboru.**
... a pripomínam, že prvá vec, ktorú urobím, keď si otvorím váš súbor, je `Session -> Restart R and run all chunks`, aby som videl, čí váš kód funguje.


