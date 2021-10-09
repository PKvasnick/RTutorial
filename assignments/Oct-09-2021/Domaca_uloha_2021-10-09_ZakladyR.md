## Domáca úloha 4/10/2021 - funkcie

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
  *Návod*: Skúste implementáciu urobiť tak, aby ste nemuseli počítať faktoriály - to je veľmi neefektívne.

- Predstavte si, že v `R` nemáme funkciu `sqrt` a napíšte funkciu, ktorá vráti odhad odmocniny x. Môžete využiť napríklad iteratívny vzťah
$$
a_{n+1} = \frac{1}{2}\left(a_n + \frac{x}{a_n}\right)
$$
​	Tento vzťah pochádza z riešenia rovnice $x-a^2=0$ Newtonovou metódou a iterácie dobre konvergujú. Odhadnite presnosť výsledku.

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



**Riešenia poprosím do víkendu pred budúcim cvičením, teda do 15. októbra vo forme odkazu na `.Rmd` súbor vo vašom GitHub repozitári.**

