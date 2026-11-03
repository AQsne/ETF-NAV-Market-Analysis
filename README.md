# ETF NAV vs. Market Price

Analyse empirique des écarts entre la valeur nette des actifs (NAV) et le prix de marché de quatre ETF américains.

## Question de recherche

Un ETF et le portefeuille sous-jacent qu’il réplique représentent une exposition proche, mais leurs prix peuvent temporairement diverger. Ce projet mesure ces primes et décotes, puis étudie leur relation avec la volatilité, le volume d’échange et la correction observée lors de la séance suivante.

## Résultats principaux

Les résultats ci-dessous proviennent de l'échantillon fusionné entre les historiques de NAV et les prix de clôture, soit **3 601 dates communes par ETF**, du **19 juin 2012 au 14 octobre 2026**.

### 1. Écarts NAV / prix de marché

| ETF | Prime/décote moyenne | Médiane | Écart absolu moyen | Écart absolu maximal | Jours > 0,25 % | Jours > 0,5 % | Jours > 1 % |
| --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| SPY | 0,0020 % | 0,0036 % | 0,0242 % | 0,9004 % | 0,3055 % | 0,0555 % | 0,0000 % |
| SPEM | 0,0759 % | 0,1046 % | 0,4514 % | 4,3401 % | 63,6768 % | 35,0736 % | 8,0533 % |
| SPIB | 0,0913 % | 0,0570 % | 0,1315 % | 6,1028 % | 15,3291 % | 3,8600 % | 0,3055 % |
| SPHY | 0,1632 % | 0,1483 % | 0,3336 % | 4,4806 % | 45,4041 % | 19,7445 % | 6,1927 % |

**Lecture des résultats :**

- **SPY** est l'ETF le plus proche de sa NAV : l'écart absolu moyen est de **0,0242 %** et dépasse 0,25 % sur seulement **0,3055 %** des jours.
- **SPEM** présente l'écart moyen le plus élevé (**0,4514 %**) et dépasse 0,25 % sur **63,6768 %** des jours.
- **SPHY** affiche également des écarts fréquents (**0,3336 %** en moyenne ; **45,4041 %** des jours au-dessus de 0,25 %).
- **SPIB** se situe entre les ETF actions et le high yield (**0,1315 %** en moyenne).
- Les primes/décotes moyennes sont positives pour les quatre ETF : le prix de marché est en moyenne légèrement supérieur à la NAV.

### 2. Effet de la volatilité

Le VIX définit les régimes suivants : volatilité faible si **VIX < 15** et forte si **VIX ≥ 30**. La comparaison porte uniquement sur ces deux régimes.

| Catégorie | Régime | Nombre de jours | Prime/décote moyenne | Écart absolu moyen |
| --- | --- | ---: | ---: | ---: |
| Actions américaines | Faible | 1 446 | 0,0023 % | 0,0202 % |
| Actions américaines | Forte | 158 | −0,0186 % | 0,0671 % |
| Actions émergentes | Faible | 1 446 | 0,1876 % | 0,3752 % |
| Actions émergentes | Forte | 158 | −0,3442 % | 0,8283 % |
| Obligations investment grade | Faible | 1 446 | 0,1214 % | 0,1314 % |
| Obligations investment grade | Forte | 158 | −0,1393 % | 0,3412 % |
| Obligations high yield | Faible | 1 446 | 0,1880 % | 0,3323 % |
| Obligations high yield | Forte | 158 | 0,0759 % | 0,5096 % |

**Résultat :** l'écart absolu moyen augmente dans les quatre catégories lorsque la volatilité passe d'un régime faible à un régime fort. L'effet est particulièrement marqué pour les actions émergentes (**0,3752 % → 0,8283 %**).

### 3. Effet du volume d'échange

Les régimes de liquidité sont définis séparément pour chaque ETF à partir des quartiles de volume. Le volume constitue un proxy imparfait de la liquidité.

| Catégorie | Régime de volume | Nombre de jours | Prime/décote moyenne | Écart absolu moyen |
| --- | --- | ---: | ---: | ---: |
| Actions américaines | Faible | 901 | 0,0067 % | 0,0199 % |
| Actions américaines | Fort | 901 | −0,0029 % | 0,0332 % |
| Actions émergentes | Faible | 901 | 0,0668 % | 0,4164 % |
| Actions émergentes | Fort | 901 | 0,0563 % | 0,5442 % |
| Obligations investment grade | Faible | 901 | 0,2398 % | 0,2503 % |
| Obligations investment grade | Fort | 901 | 0,0304 % | 0,0618 % |
| Obligations high yield | Faible | 903 | 0,1574 % | 0,4625 % |
| Obligations high yield | Fort | 901 | 0,1088 % | 0,1722 % |

**Résultat :** l'effet du volume est hétérogène. L'écart augmente avec le volume pour les actions américaines et émergentes, tandis qu'il diminue pour les obligations : **0,2503 % → 0,0618 %** pour SPIB et **0,4625 % → 0,1722 %** pour SPHY.

### 4. Correction lors de la séance suivante

Les observations retenues sont celles dont l'écart absolu est supérieur ou égal à **0,25 %**. Une correction correspond à une diminution de l'écart absolu le jour suivant.

| ETF | Dates analysées | Taux de correction | Variation moyenne de l'écart à 1 jour |
| --- | ---: | ---: | ---: |
| SPY | 11 | 100,0000 % | −0,3203 point de pourcentage |
| SPEM | 2 292 | 68,6736 % | −0,1663 point de pourcentage |
| SPHY | 1 635 | 67,2783 % | −0,1050 point de pourcentage |
| SPIB | 552 | 65,2174 % | −0,0526 point de pourcentage |

**Résultat :** les écarts importants diminuent lors de la séance suivante dans la majorité des cas. Le résultat de **SPY** doit être interprété avec prudence, car il repose sur seulement **11 observations**.

### Conclusion empirique

Les écarts entre la NAV et le prix de marché restent faibles pour SPY, mais deviennent plus importants pour les ETF exposés aux marchés émergents et aux obligations high yield. Ils s'amplifient généralement lorsque la volatilité est forte et tendent souvent à se réduire dès la séance suivante. Ces résultats décrivent des régularités statistiques dans l'échantillon ; ils n'établissent pas une relation de causalité.

## Sources et limites

- NAV : [State Street Global Advisors — ETF fund data](https://www.ssga.com/us/en/intermediary/etfs/resources/fund-data)
- Prix et volumes : [Yahoo Finance](https://finance.yahoo.com/)
- Volatilité : indice VIX téléchargé via Yahoo Finance

La NAV et le cours de clôture peuvent correspondre à des horaires ou conventions de valorisation différents. Le volume est un proxy imparfait de la liquidité et l’analyse décrit des associations, sans établir de causalité.
