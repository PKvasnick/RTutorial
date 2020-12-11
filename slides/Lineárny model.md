# Lineárny model

Tento dokument slúži na rýchlu rekapituláciu toho, čo ste sa dávnejšie učili na štatistike. Chcem zaviesť formalizmus a označenia, ktoré vám lepšie pomôžu chápať, čo počíta R, keď použijete funkciu `lm`.

## Definícia

Majme nezávisle premenné  $\mathbf{x_1}, \mathbf{x_2}, \dots, \mathbf{x_m}$, kde
$$
\begin{align}
    \mathbf{x_i} &= \begin{pmatrix}
           x_{1i} \\
           x_{2i} \\
           \vdots \\
           x_{ni}
         \end{pmatrix}
  \end{align}
$$
a závisle premennú $\mathbf{y}$, 
$$
\begin{align}
    \mathbf{y} &= \begin{pmatrix}
           y_{1} \\
           y_{2} \\
           \vdots \\
           y_{m}
         \end{pmatrix}
  \end{align}
$$
_*Lineárny model*_ premennej $\mathbf{y}$ v termínoch vysvetľujúcich premenných $\mathbf{x_i}, i=1,\dots, m$ je závislosť tvaru
$$
\mathbf{y} = \beta_1 \mathbf{x_1} + \beta_2 \mathbf{x_2} + \dots + \beta_m \mathbf{x_m} + \mathbf{\epsilon}
$$
kde 
$$
\begin{align}
    \mathbf{\beta} &= \begin{pmatrix}
           \beta_{1} \\
           \beta_{2} \\
           \vdots \\
           \beta_{m}
         \end{pmatrix}
\end{align}
$$
je vektor parametrov a 
$$
\begin{align}
	\mathbf{\epsilon} &= \begin{pmatrix}
		\epsilon_1 \\
		\epsilon_2 \\
		\vdots \\
		\epsilon_n
	\end{pmatrix}
\end{align}
$$

je vektor náhodných chýb merania. O ňom typicky predpokladáme, že jeho zložky sú _*iid*_ (independent identically distributed) náhodné premenné s nulovou strednou hodnotou a varianciou $\sigma^2$.

### Maticová forma

V maticovej forme môžeme lineárny model zapísať takto:
$$
\mathbf{y} = \mathbf{F}\mathbf{\beta} + \mathbf{\epsilon},
$$
kde $\mathbf{F}$ je _*faktorová matica*_ $(n \times m)$, vytvorená z vektorov vysvetľujúcich premenných, 
$$
\mathbf{F} = 
\begin{pmatrix}
x_{1,1} & x_{1,2} & \cdots & x_{1,m} \\
x_{2,1} & x_{2,2} & \cdots & x_{2,m} \\
\vdots  & \vdots  & \ddots & \vdots  \\
x_{n,1} & x_{n,2} & \cdots & x_{n,m} 
\end{pmatrix}
$$
Prvý faktor býva často konštantný, teda 
$$
\begin{align}
    \mathbf{x_1} &= \begin{pmatrix}
           1 \\
           1 \\
           \vdots \\
           1
         \end{pmatrix}
  \end{align}
$$
a často ho do modelu pridáva automaticky software. 

Od vektorov $\mathbf{x_i},\enspace i=1,2,\dots m$ požadujeme, aby boli lineárne nezávislé, teda aby priestor, ktorý vytvárajú, mal dimenziu $m$.

### Spojité a diskrétne vysvetľujúce premenné

Vysvetľujúce premenné môžu byť veľmi rôzne:

* _Spojité_ premenné sú najobvyklejší prípad, pod ktorý patrí obyčajná lineárna regresia.
* Diskrétne premenné vedú k modelom, ktoré ste asi zvykli označovať ako analýza roztpylu, čiže ANOVA.
* Kombinácia spojitých a diskrétnych premenných vedie k modelom, ktoré ste najskôr označovali ako analýza kovariancie alebo ANCOVA. 
* Transformáciou výstupnej premennej $\mathbf{y}$ na spojitú premennú vieme na tvar lineárneho modelu previesť celý rad dôležitých druhov modelov (logistická, poissonovská regresia a pod.)
* Špeciálnym prípadom lineárnych modelov sú časové rady, kedy parametrami modelu sú premenné $\mathbf{x}$ a $\mathbf{y}$, posunuté o istý počet prvkov dozadu - modely ARIMA.

### Čo znamená _lineárny_

_*Lineárny*_ v pomenovaní "lineárny model" znamená _*lineárny v parametroch*_ a teda nie lineárny vo faktoroch. 
$$
y_i = \beta_0 + \beta_1 x_i + \beta_2 x_i^2 + \epsilon_i, \quad y_i = \beta_1 \sin(\phi_i) + \beta_2 \cos(\phi_i) + \epsilon_i
$$
sú lineárne modely. 

Linearita modelu má tri dôležité dôsledky:

1. Ak hľadáme koeficienty minimalizáciou súčtu kvadrátov odchýlok, 
   $$
   S^2 = Tr\left[(\mathbf{y} - \mathbf{F\beta})(\mathbf{y} - \mathbf{F\beta})^T\right]
   $$
   potom $S^2$ je kvadratická forma v parametroch $\mathbf{\beta}$ a jej derivácie podľa parametrov sú lineárnymi funkciami parametrov $\mathbf{\beta}$. To znamená, že parametre modelu vieme ľahko vypočítať.

2. Optimálne parametre $\mathbf{\beta}$ sú lineárnymi funkciami dát $\mathbf{y}$.
3. Optimálne parametre $\mathbf{\beta}$ sú lineárnymi funkciami náhodných šumov $\mathbf{\epsilon}$, vďaka čomu vieme mimoriadne ľahko odvodiť ich štatistické vlastnosti. 

_*Poznámka*_ $Tr$ je stopa matice, čiže súčet jej diagonálnych prvkov, $Tr(\mathbf{A}) = \sum_{i} A_{i,i}$.

### Identifikácia modelu

Identifikácia lineárneho modelu je úloha určiť parametre $\beta_0, \beta_1,  \dots, \beta_m$ a ich štatistické vlastnosti. U lineárneho modelu hľadáme parametre minimalizáciou súčtu štvorcov odchýlok pozorovaných hodnôt od predpovedí modelu:
$$
\mathbf{e} = \mathbf{y}-\mathbf{F\beta} \\
S^2 = Tr(\mathbf{ee^T}) \\
\mathbf{\beta} = argmin \left(S^2(\mathbf{\beta})\right)
$$
Poďme to urobiť:
$$
\frac{dS^2}{d\mathbf{\beta}} = \frac{d}{d\mathbf{\beta}}Tr\left[\left(\mathbf{y} - \mathbf{F\beta}\right)\left(\mathbf{y} - \mathbf{F\beta}\right)^T\right] = \\
= \frac{d}{d\mathbf{\beta}}Tr\left[\mathbf{yy^T} - \mathbf{y\beta^TF^T - \mathbf{F\beta y^T} + \mathbf{F\beta\beta^TF^T}}\right]
$$
Uvedomíme si, že stopa sa nemení pri transpozícii matice ani pri cyklickej zámene v súčine matíc, potom máme
$$
Tr\left(\mathbf{y\beta^TF^T}\right) = Tr\left(\mathbf{F\beta y^T}\right);
$$
okrem toho [(Maticová algebra)](https://tminka.github.io/papers/matrix/minka-matrix.pdf)
$$
\frac{d}{d\mathbf{X}}Tr(\mathbf{AXB}) = \mathbf{BA}, \\
\frac{d}{d\mathbf{X}}Tr(\mathbf{AX^TBXC}) = \mathbf{CAX^TB}+\mathbf{A^TC^TX^TB^T}
$$
Odkiaľ vyplývajú takéto veci? 
$$
dTr(\mathbf{AXB}) = Tr(\mathbf{AdXB})=Tr(\mathbf{BAdX}) = Tr(\mathbf{BA})\mathbf{dX}
$$
a podobne pre druhý výraz - treba si uvedomiť, že derivácia skalára podľa matice je matica. 

S využitím týchto vzťahov máme
$$
\frac{d}{d\mathbf{\beta}}Tr\left[\mathbf{yy^T} - \mathbf{y\beta^TF^T - \mathbf{F\beta y^T} + \mathbf{F\beta\beta^TF^T}}\right] = \mathbf{0} - 2\mathbf{y^TF} + 2\mathbf{\beta^TF^TF}
$$
pretože $\mathbf{FF^T}$ je symetrická matica. Odtiaľ konečne 
$$
\mathbf{\hat{\beta}} = (\mathbf{F^TF})^{-1}\mathbf{F^Ty}
$$
ak matica $\mathbf{F^TF}$ nie je singulárna.

Takto sme dostali výraz pre koeficienty, ale tu nekončíme, chceme poznať kovariancie koeficientov aj rezíduí. Na to jednoducho dosadíme $\mathbf{y} = \mathbf{F\beta + \epsilon}$:
$$
cov({\mathbf{\hat{\beta}}}) = (\mathbf{\hat{\beta} - \beta})(\mathbf{\hat{\beta} - \beta})^T = (\mathbf{F^TF})^{-1}\mathbf{F^T\epsilon\epsilon^TF}(\mathbf{F^TF})^{-1}=(\mathbf{F^TF})^{-1}\sigma^2
$$
a diagonálne elementy tejto matice sa štandardne uvádzajú ako chyby koeficientov. 

Predpovede modelu sú 
$$
\mathbf{\hat{y}} = \mathbf{F\hat{\beta}} = \mathbf{F(F^TF)^{-1}F^Ty} \equiv \mathbf{Hy}
$$
kde matica $\mathbf{H}$ sa často nazýva _*hat matrix*_ a je to projektor do podpriestoru, vytvoreného faktormi regresie - ľahko overíte, že $\mathbf{H^2}=\mathbf{H}$.

Rezíduá regresie sú 


$$
\mathbf{r}\equiv \mathbf{y - F\hat{\beta}} = \mathbf{y - Hy} = (\mathbf{1-H})\mathbf{y} = (\mathbf{1-H})\mathbf{\epsilon} \\
cov(\mathbf{r}) = \mathbf{rr^T} = (\mathbf{1-H})\mathbf{\epsilon\epsilon^T}(\mathbf{1-H}) = (\mathbf{1-H})\sigma^2
$$
pretože aj $\mathbf{1-H}$ je projekčná matica, ktorá projektuje veci do reziduálneho podpriestoru (ortogonálneho na priestor vysvetľujúcich premenných).

Takto sme spočítali základné veci pre lineárnu regresiu, pričom sme zatiaľ nikde nepoužili predpoklad o Gaussovskom rozdelení. 