# ETF NAV vs. Market Price

Analyse empirique des écarts entre la valeur nette des actifs (NAV) et le prix de marché de quatre ETF américains.

## Question de recherche

Un ETF et le portefeuille sous-jacent qu’il réplique représentent une exposition proche, mais leurs prix peuvent temporairement diverger. Ce projet mesure ces primes et décotes, puis étudie leur relation avec la volatilité, le volume d’échange et la correction observée lors de la séance suivante.

## Résultats principaux

L’analyse porte sur **SPY**, **SPEM**, **SPIB** et **SPHY**, représentant respectivement les actions américaines, les actions émergentes, les obligations investment grade et les obligations high yield.

| ETF | Écart absolu moyen | Jours avec écart ≥ 0,25 % |
| --- | ---: | ---: |
| SPY | 0,0242 % | 0,31 % |
| SPIB | 0,1315 % | 15,33 % |
| SPHY | 0,3336 % | 45,40 % |
| SPEM | 0,4514 % | 63,68 % |

Les écarts augmentent dans les régimes de forte volatilité, notamment pour SPEM (**0,3752 % → 0,8283 %**). Parmi les écarts importants, une diminution est observée dès la séance suivante dans **65,22 % à 100 %** des cas selon l’ETF, avec une prudence particulière pour SPY, dont le résultat ne repose que sur 11 observations.

## Sources et limites

- NAV : [State Street Global Advisors — ETF fund data](https://www.ssga.com/us/en/intermediary/etfs/resources/fund-data)
- Prix et volumes : [Yahoo Finance](https://finance.yahoo.com/)
- Volatilité : indice VIX téléchargé via Yahoo Finance

La NAV et le cours de clôture peuvent correspondre à des horaires ou conventions de valorisation différents. Le volume est un proxy imparfait de la liquidité et l’analyse décrit des associations, sans établir de causalité.
