## Domáca úloha 16/10/2020 - funkcie

- Napíšte funkciu s nasledujúcou signatúrou

  ```{r}
  combin <- function(n,k)
  {
  	...
  }
  ```
  ktorá vracia kombinačné číslo 
  $$
  n \choose k
  $$

- Napíšte funkciu s nasledujúcou signatúrou

  ```{r}
  integ <- function(f, a, b)
  {
  	...    
  }
  ```
  ktorá vypočíta odhad určitého integrálu 
  $$
  \int_a^b f(x)dx
  $$
  a jeho chybu - teda vracia dve hodnoty. Toto sa v R robí tak, že vrátite zoznam `r`, pričom `r$integral` bude hodnota a `r$error` jej chyba.  

- Napíšte funkciu so signatúrou 
  
  ```{r}
  clear.dia <- function(s)
  {
    ...
  }
  ```
  ktorá nahradí znaky s diakritikou v textovom reťazci príslušnými znakmi bez diakritiky, teda napríklad
  `Čučoriedka` -> `Cucoriedka`
  
  __Návod__: Najjednoduchšie je použiť prekladový "slovník" pre náhradu znakov. 

U každej funkcie ilustrujte na rozumnom počte príkladov, že vaša implementácia funguje.  Nepotrebujem žiadne extra precízne či efektívne implementácie, iba niečo, čo v zásade funguje. 



**Riešenia poprosím do budúceho piatku 23. októbra vo forme `.Rmd` súboru.**


