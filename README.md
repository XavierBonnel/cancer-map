# Cancer France — Carte d'incidence interactive

Carte interactive de l'incidence du cancer en France, basée sur les taux standardisés (population mondiale) pour 100 000 personnes-années. Les données proviennent des registres Francim et sont publiées par Santé Publique France via la plateforme [Odissé](https://odisse.santepubliquefrance.fr/).

## Aperçu

L'application affiche, à l'échelle départementale, le taux d'incidence du cancer (tous types confondus) pour les départements couverts par un registre Francim — soit environ 22 à 25 % de la population hexagonale, plus 3 départements et régions d'outre-mer (DROM).

### Fonctionnalités

- **Filtres d'affichage** :
  - Hommes + Femmes (combiné)
  - Hommes seuls
  - Femmes seules
  - Ratio Hommes / Femmes
- **Périodes disponibles** : de 1988-1992 à 2018-2022 (par tranches de 5 ans)
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

- **Registres Francim** — Réseau français des registres des cancers
- **Santé Publique France / Odissé** : [Cancer — incidence observée en zone registres (département)](https://odisse.santepubliquefrance.fr/catalog/datasets/cancer-incidence-observee-en-zone-registres-departement/)

## Limites

- Seuls les départements disposant d'un registre exhaustif Francim sont représentés ; les zones en gris ne disposent pas de données comparables.
- Les taux sont **standardisés sur la population mondiale**, ce qui permet la comparaison entre départements et entre périodes, mais ne reflète pas l'incidence brute observée localement.
