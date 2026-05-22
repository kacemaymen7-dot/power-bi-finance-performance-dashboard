# Finance Performance Dashboard — Projet Power BI

## 1. Présentation du projet

Ce projet est un dashboard Power BI Finance réalisé dans le cadre de ma préparation à la certification **PL-300 Power BI Data Analyst**.

L’objectif du projet est d’analyser la performance financière d’une entreprise à partir de données **réelles vs budget**.

Le dashboard permet de suivre les principaux indicateurs financiers :

- chiffre d’affaires ;
- coûts ;
- profit ;
- marge ;
- taux d’atteinte du budget ;
- écarts entre budget et réalisé ;
- tendances temporelles.

Ce projet démontre un workflow complet Power BI :

- nettoyage des données avec Power Query ;
- modélisation en schéma en étoile ;
- création de mesures DAX ;
- analyse Budget vs Actual ;
- analyse temporelle avec YTD, MoM et YoY ;
- création d’un dashboard interactif ;
- mise en place d’une Row-Level Security dans Power BI Desktop.

---

## 2. Objectif business

L’objectif business de ce dashboard est d’aider une équipe finance ou management à suivre la performance de l’entreprise et à identifier les écarts entre les résultats réels et les objectifs budgétaires.

Le rapport permet de répondre à plusieurs questions clés :

- Quel est le chiffre d’affaires total ?
- Quel est le coût total ?
- Quel est le profit ?
- Quelle est la marge ?
- L’entreprise atteint-elle ses objectifs de budget ?
- Quelles régions, départements ou produits performent le mieux ?
- Où se trouvent les principaux écarts budgétaires ?
- Comment la performance évolue-t-elle dans le temps ?

---

## 3. Outils utilisés

Les outils utilisés dans ce projet sont :

- **Power BI Desktop**
- **Power Query**
- **DAX**
- **Excel**
- **Modélisation de données**
- **Row-Level Security dans Power BI Desktop**

---

## 4. Dataset

Le projet utilise un dataset financier simulé, créé pour un usage d’apprentissage et de portfolio.

Le dataset contient :

- données de revenus réels ;
- données de coûts réels ;
- données de budget revenu ;
- données de budget coût ;
- table calendrier ;
- table des régions ;
- table des départements ;
- table des produits.

Les principales tables utilisées sont :

- `Raw_Actuals_Clean`
- `Raw_Budget_Clean`
- `Dim_Date_Calendar`
- `Dim_Region`
- `Dim_Department`
- `Dim_Product`

---

## 5. Préparation des données

Les données ont été nettoyées et transformées avec **Power Query**.

Les principales étapes de préparation incluent :

- suppression des lignes vides ;
- suppression des doublons pertinents ;
- correction des types de données ;
- nettoyage des espaces dans les colonnes de codes ;
- standardisation des codes région, département et produit ;
- correction des valeurs incohérentes ;
- préparation des tables de faits propres pour l’analyse.

Cette étape permet de garantir une meilleure qualité des données avant la modélisation et la création des mesures DAX.

---

## 6. Modèle de données

Le projet utilise un modèle en **schéma en étoile**.

### Tables de faits

- `Raw_Actuals_Clean`
- `Raw_Budget_Clean`

### Tables de dimensions

- `Dim_Date_Calendar`
- `Dim_Region`
- `Dim_Department`
- `Dim_Product`

Les dimensions filtrent les tables de faits via des relations :

- cardinalité **un à plusieurs** ;
- filtre croisé en direction **simple** ;
- relations actives entre dimensions et faits.

Ce modèle permet une analyse claire, stable et adaptée aux bonnes pratiques Power BI.

---

## 7. Mesures DAX principales

Les principales mesures DAX créées dans ce projet sont :

- `Total Revenue`
- `Total Cost`
- `Total Budget Revenue`
- `Total Budget Cost`
- `Profit`
- `Profit Margin %`
- `Variance Revenue`
- `Variance Revenue %`
- `Variance Cost`
- `Variance Cost %`
- `Budget Achievement %`
- `Revenue YTD`
- `Budget Revenue YTD`
- `Revenue MoM %`
- `Revenue YoY %`
- `Profit YTD`
- `Profit MoM %`
- `Profit YoY %`

Ces mesures permettent d’analyser la performance financière, les écarts budgétaires et les tendances dans le temps.

---

## 8. Pages du dashboard

Le rapport contient les pages suivantes :

### 1. Executive Summary

Page de synthèse permettant de visualiser rapidement les principaux KPI :

- Total Revenue ;
- Profit ;
- Profit Margin % ;
- Budget Achievement % ;
- Variance Revenue % ;
- Revenue YoY %.

Cette page donne une vision rapide de la performance globale.

### 2. Budget vs Actual Analysis

Page dédiée à la comparaison entre le réel et le budget.

Elle permet d’analyser :

- Revenue vs Budget Revenue ;
- Cost vs Budget Cost ;
- Variance Revenue ;
- Variance Cost ;
- Budget Achievement %.

### 3. Dimension Analysis

Page dédiée à l’analyse par dimension :

- région ;
- département ;
- produit.

Elle permet d’identifier les zones, départements ou produits les plus performants.

### 4. Time Intelligence Analysis

Page dédiée à l’analyse temporelle :

- YTD ;
- MoM ;
- YoY ;
- tendances mensuelles ;
- évolution de la performance.

### 5. Drillthrough Details

Page de détail permettant d’analyser une région sélectionnée avec un niveau plus fin par département et produit.

---

## 9. Insights business

### Insight 1 — Revenue vs Budget

Le revenu réel reste globalement proche du budget prévu. Les périodes ou régions avec une variance négative doivent être analysées pour comprendre les causes des écarts.

### Insight 2 — Profitabilité

La marge montre une rentabilité globalement solide. Les départements ou produits avec une marge plus faible doivent être étudiés afin d’identifier des pistes d’amélioration.

### Insight 3 — Variance des coûts

Certains coûts peuvent dépasser le budget prévu et réduire le profit. Les départements avec une variance cost positive doivent être suivis régulièrement.

### Insight 4 — Performance régionale

La contribution au revenu et au profit varie selon les régions. Les régions les moins performantes peuvent nécessiter des actions commerciales plus ciblées.

### Insight 5 — Tendance temporelle

Les indicateurs YTD, MoM et YoY permettent de suivre l’évolution de la performance dans le temps et d’identifier les périodes de croissance ou de ralentissement.

---

## 10. Interactivité

Le dashboard contient plusieurs éléments interactifs :

- slicers par année ;
- slicers par région ;
- slicers par département ;
- slicers par produit ;
- tooltips enrichis ;
- drillthrough par région ;
- bouton retour sur la page de détail.

Les slicers proviennent des tables de dimensions afin de garantir un filtrage propre du modèle.

---

## 11. Row-Level Security

Une sécurité **Row-Level Security** a été créée dans Power BI Desktop.

Exemple de rôle :

- `North Manager`

Ce rôle filtre les données afin de montrer uniquement les informations liées à la région **North**.

Cette fonctionnalité permet de démontrer la capacité à sécuriser un rapport selon le rôle de l’utilisateur.

---

## 12. Limites du projet

Ce projet utilise un dataset simulé pour un usage d’apprentissage et de portfolio.

Le rapport a été développé dans **Power BI Desktop**.

La publication dans Power BI Service, le refresh planifié et l’assignation réelle des utilisateurs aux rôles RLS n’ont pas été entièrement mis en place, car aucun environnement Power BI professionnel n’était disponible.

---

## 13. Améliorations possibles

Les prochaines améliorations possibles sont :

- publication du rapport dans Power BI Service ;
- configuration d’un refresh planifié ;
- assignation réelle des utilisateurs aux rôles RLS ;
- connexion à une vraie base de données d’entreprise ;
- ajout de KPI financiers plus avancés ;
- amélioration du design visuel ;
- création d’une page dédiée aux insights business ;
- automatisation de l’actualisation des données.

---

## 14. Compétences démontrées

Ce projet démontre plusieurs compétences importantes pour un Data Analyst Power BI :

- nettoyage des données avec Power Query ;
- modélisation en schéma en étoile ;
- création de mesures DAX ;
- analyse Budget vs Actual ;
- Time Intelligence ;
- création de dashboards interactifs ;
- Drillthrough ;
- Row-Level Security ;
- communication d’insights business.

---

## 15. Conclusion

Ce projet Power BI Finance Dashboard démontre un workflow complet d’analyse de données avec Power BI.

Il permet d’analyser la performance financière d’une entreprise, d’identifier les écarts budgétaires, de suivre les tendances temporelles et de communiquer des insights business utiles.

Ce projet constitue un élément de portfolio pertinent pour des rôles comme :

- Data Analyst ;
- Power BI Analyst ;
- BI Analyst junior ;
- Consultant Power BI junior ;
- FP&A Analyst junior.
