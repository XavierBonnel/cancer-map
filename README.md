# Cancer France — Carte d'incidence interactive

Carte interactive de l'incidence du cancer en France, basée sur les taux standardisés (population mondiale) pour 100 000 personnes-années.

- **Données observées** : registres Francim (~21 départements) — Santé Publique France / [Odissé](https://odisse.santepubliquefrance.fr/)
- **Données estimées (2007-2016)** : **98 départements** — modèle multi-source (PMSI + ALD + registres) publié par Santé Publique France

## Aperçu

L'application propose **deux modes** :

1. **📊 Estimé 2007-2016** — couvre **98 départements** (France métropolitaine + Guadeloupe, Martinique, Guyane). Données modélisées à partir du PMSI, des ALD et des registres Francim.
2. **🔬 Observé (1988-2022)** — couvre les **~21 départements** avec registre Francim exhaustif. Données collectées directement par les registres.

### Fonctionnalités

- **Filtres d'affichage** :
  - Hommes + Femmes (combiné)
  - Hommes seuls
  - Femmes seules
  - Ratio Hommes / Femmes
- **Périodes disponibles** : de 1988-1992 à 2018-2022 (observé) + 2007-2016 (estimé — tous départements)
- **Indicateur de source** : chaque département affiche « Estimé (modèle) » ou « Observé (registre) » dans l'infobulle
- **Compteur dynamique** : nombre de départements affichés selon la période sélectionnée
- **Carte interactive** : survol des départements pour afficher les détails, légende et code couleur selon l'intensité du taux

## Utilisation

Le projet est une application web statique d'un seul fichier. Aucun build, aucune dépendance à installer.

```bash
# Ouvrir directement dans un navigateur
open index.html

# Ou servir localement
python3 -m http.server 8000
```

Puis naviguer vers `http://localhost:8000`.

## Pile technique

- **HTML / CSS / JavaScript** vanilla
- **[Leaflet](https://leafletjs.com/)** 1.9.4 (cartographie interactive) chargé via CDN
- Données géographiques et statistiques intégrées directement dans `index.html`

## Source des données

- **Registres Francim** — Réseau français des registres des cancers (données observées)
- **Santé Publique France / Odissé** :
  - [Cancer — incidence observée en zone registres (département)](https://odisse.santepubliquefrance.fr/catalog/datasets/cancer-incidence-observee-en-zone-registres-departement/)
  - [Cancer — incidence et mortalité estimées par département](https://odisse.santepubliquefrance.fr/catalog/datasets/cancer-incidence-et-mortalite-estimees-departement/) (modèle multi-source 2007-2016)

## Limites

- Les données **observées** (registres Francim) ne couvrent qu'environ 22-25 % de la population française ; le mode « Estimé 2007-2016 » utilise un modèle statistique pour couvrir les 98 départements.
- Les données **estimées** datent de la période 2007-2016 (dernière publication disponible). Les périodes plus récentes (2018-2022) ne sont disponibles que pour les départements avec registre.
- Les taux sont **standardisés sur la population mondiale**, ce qui permet la comparaison entre départements et entre périodes, mais ne reflète pas l'incidence brute observée localement.
- Pour les données estimées, les valeurs de taux brut (ra) et de nombre de cas (k) ne sont pas disponibles — seul le taux standardisé Monde (rm) est fourni.
