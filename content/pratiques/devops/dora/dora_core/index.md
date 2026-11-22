+++
title = "Dora Core Model"
description = "Le DORA Core rassemble les capacités, les métriques et les résultats les mieux établis par les années de recherche de DORA."
weight = 10
+++

> [!definition] Définition
> DORA Core is a collection of [capabilities]({{< relref "capabilities" >}}), [metrics]({{< relref "metriques" >}}), and outcomes that represent the most firmly-established findings from across the history and breadth of DORA’s research program.

![](https://dora.dev/research/core/assets/dora-core-v2.0.0-detail.png)

## Lire le schéma de gauche à droite

Le modèle se lit comme une chaîne de cause à effet :

```
Capabilities  ──►  Métriques de livraison  ──►  Résultats
(ce qu'on fait)    (débit et stabilité)          (ce qu'on obtient)
```

1. **Capabilities** : les pratiques de l'équipe. Intégration continue, tests automatisés, petits lots, culture d'apprentissage…
2. **Métriques** : elles mesurent la performance de livraison, selon deux axes :
   - le **débit** : à quelle vitesse un changement arrive en production ;
   - la **stabilité** : est-ce que ce changement casse quelque chose.
3. **Résultats** (*outcomes*) : ce qui intéresse vraiment l'organisation. Performance de l'entreprise, performance de l'équipe, bien-être des personnes.

> [!warning] Attention
> On n'agit pas directement sur les métriques. On agit sur les capabilities, et les métriques indiquent si cela produit un effet. Viser le chiffre pour lui-même mène aux dérives décrites par la loi de Goodhart.
