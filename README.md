# Analyse des sources de trafic non rentables et réaffectation du budget pour Yandex.Afisha

## Objectif du projet :
Aider les spécialistes du marketing de Yandex Afisha à réduire les dépenses en abandonnant les sources de trafic non rentables et en réallouant le budget.

Il est nécessaire d'étudier :
* Comment les clients utilisent le service,
* Quand ils effectuent leur premier achat sur le site,
* Combien d'argent chaque client rapporte à l'entreprise,
* Quand les dépenses pour attirer un client sont rentables.

*Les revenus sont mesurés en unités de monnaie virtuelle - u.m.*

## Stack du Projet :

* Analyse de cohortes
* Économie unitaire
* Métriques de produit

**Bibliothèques Python utilisées :**
    * `pandas`
    * `numpy`
    * `matplotlib.pyplot`
    * `seaborn`

## Résultat final :

1. Les métriques produit ont été calculées : `dau`, `wau`, `mau`, fréquence moyenne des visites par jour par utilisateur, durée moyenne de session utilisateur, taux de rétention.
2. Les métriques de commerce électronique ont été calculées : temps moyen entre la première visite et l'achat, nombre moyen d'achats en six mois, panier moyen, `LTV`.
3. Les métriques marketing ont été calculées : dépenses marketing par source, `CAC`, `romi` par cohorte par source.
4. Sur la base des métriques calculées, une redistribution du budget vers les sources ayant la croissance cumulative `romi` et `LTV` la plus rapide a été proposée.
5. Les canaux de trafic non rentables ont été identifiés.

## Description des données

Les données proviennent de Yandex.Afisha et couvrent la période de juin 2017 à la fin mai 2018 :
* Les journaux de serveur contenant des informations sur les visites du site Yandex.Afisha,
* L'extraction de toutes les commandes passées pendant cette période,
* Les statistiques des dépenses publicitaires.

Le fichier `visits_log.csv` contient les journaux du serveur avec des informations sur les visites du site, `orders_log.csv` contient des informations sur les commandes, et `costs.csv` contient des informations sur les dépenses marketing.

Structure de `visits_log.csv` :
* `Uid` — identifiant unique de l'utilisateur,
* `Device` — catégorie de l'appareil de l'utilisateur,
* `Start Ts` — date et heure du début de la session,
* `End Ts` — date et heure de la fin de la session,
* `Source Id` — identifiant de la source de trafic vers le site.

---

Structure du fichier `orders_log.csv`
* `Uid` - Identifiant unique de l'utilisateur,
* `Buy Ts` - Date et heure de la commande,
* `Revenue` - Montant de la commande.

---

Structure du fichier `costs.csv`
* `source_id` - Identifiant de la source publicitaire,
* `dt` - Date de la campagne publicitaire,
* `costs` - Dépenses pour cette campagne.
