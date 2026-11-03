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

## Méthodologie

1. Téléchargement et nettoyage des historiques de NAV publiés par State Street Global Advisors.
2. Téléchargement des prix de clôture et des volumes via Yahoo Finance.
3. Fusion des observations communes entre NAV et prix de marché.
4. Calcul de la prime/décote :

   \[
   \mathrm{Prime/Décote}_t = \frac{P^{marché}_t - NAV_t}{NAV_t} \times 100
   \]

5. Comparaison des écarts selon des régimes de VIX et des quartiles de volume propres à chaque ETF.
6. Mesure de la correction le jour suivant pour les écarts absolus supérieurs ou égaux à 0,25 %.

## Structure

```text
.
├── notebooks/
│   └── etf_nav_market_price_analysis.ipynb
├── requirements.txt
└── README.md
```

## Reproduire l’analyse

```bash
python -m venv .venv

# Windows
.venv\Scripts\activate

# macOS / Linux
source .venv/bin/activate

pip install -r requirements.txt
jupyter notebook notebooks/etf_nav_market_price_analysis.ipynb
```

Le notebook télécharge les données au moment de l’exécution ; aucun fichier de données propriétaire ou volumineux n’est stocké dans le dépôt. Les résultats présentés ci-dessus correspondent à la dernière exécution du notebook et peuvent évoluer lorsque les fournisseurs mettent à jour leurs historiques.

## Sources et limites

- NAV : [State Street Global Advisors — ETF fund data](https://www.ssga.com/us/en/intermediary/etfs/resources/fund-data)
- Prix et volumes : [Yahoo Finance](https://finance.yahoo.com/)
- Volatilité : indice VIX téléchargé via Yahoo Finance

La NAV et le cours de clôture peuvent correspondre à des horaires ou conventions de valorisation différents. Le volume est un proxy imparfait de la liquidité et l’analyse décrit des associations, sans établir de causalité.

> Projet académique réalisé dans le cadre du cursus Python de l’ENSAE Paris. Ce dépôt ne constitue pas un conseil en investissement.
