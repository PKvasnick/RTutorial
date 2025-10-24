## Domáca úloha 23-10-2025

1. Napíšte kus R, ktorý vytvorí takúto maticu:

$$
M = \begin{pmatrix}
	0 & 1 & 2 & 3 & 4 \\
	1 & 2 & 3 & 4 & 0 \\
	2 & 3 & 4 & 0 & 1 \\
	3 & 4 & 0 & 1 & 2 \\
	4 & 0 & 1 & 2 & 3 
\end{pmatrix}
$$

Návod: pozrite sa, čo robia funkcie `cbind` a `rbind`.

**Riešenie** môže vyzerať napríklad takto:

```R
rotate <- function(a) {
  n = length(a)
  return(c(a[2:n],a[1]))
}

vec <- 0:4
n <- length(vec)
mat = cbind(vec)
for(k in 2:n) {
  vec <- rotate(vec)
  mat = cbind(mat, vec)
}
print(mat)
```

2. Pozrite sa na dáta `Orange` v knižnici `datasets` a skúste ich čo najlepšie nakresliť. Váš skript by mal začínať nejako takto:

```R
library(tidyverse)	# pre ggplot
library(datasets)	# pre Orange

print(summary(Orange))

ggplot(data = Orange) +
	...
```

Samozrejme vám pomôže `help(Orange)` alebo `summary(Orange)`.

**Riešenie** závisí od vás, môžete napríklad chcieť pridať nadpis, popisky osí a pod.. Môžete napríklad nakresliť toto:

```R
library(datasets)
library(tidyverse)

ggplot(data = Orange) + 
  geom_boxplot(mapping = aes(x = as.factor(age), y = circumference)) +
  geom_jitter(mapping = aes(x = as.factor(age), y = circumference, color = Tree), width = 0.2, size = 2) +
  theme_bw()


```

`as.factor(age)` potrebujeme preto, že na x-ovej osi musia byť diskrétne kategórie, aby `ggplot` dokázal roztriediť dáta pre jednotlivé boxploty. 

Podobne sa môžete pozrieť aj na ďallšie dáta, napr. `Indometh`, `ChickWeight` a pod. Zoznam získate ľahko, `help(datasets)`.