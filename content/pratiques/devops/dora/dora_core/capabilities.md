+++
title = "Capabilities (Capacités)"
description = "Le catalogue des capacités DORA : les pratiques techniques, culturelles et de pilotage qui améliorent la performance de livraison."
weight = 20
+++

> [!ressource] Ressources
> - [Capability catalog](https://dora.dev/capabilities/)

## Qu'est-ce qu'une capability ?

Une *capability* est une **pratique ou une condition de travail** dont la recherche DORA a montré qu'elle améliore la performance de livraison. Ce sont les leviers sur lesquels l'équipe agit ; les [métriques]({{< relref "metriques" >}}) indiquent ensuite si cela fonctionne.

## Trois familles

| Famille | Exemples | Effet principal |
| --- | --- | --- |
| **Techniques** | Intégration continue, trunk-based development, tests automatisés, déploiement automatisé, architecture faiblement couplée | Livrer souvent sans casser |
| **Processus** | Petits lots (*small batches*), flux de travail visible, retours clients, approbation légère des changements | Réduire l'attente et la taille des changements |
| **Culture** | Culture générative (Westrum), apprentissage, autonomie, bien-être | Rendre les autres pratiques possibles et durables |

## Le lien avec débit et stabilité

Chaque capability agit sur l'un des deux axes, et souvent sur les deux :

- **Petits lots** : un petit changement passe vite (débit) et casse moins, ou casse de façon facile à diagnostiquer (stabilité).
- **Déploiement automatisé** : déployer devient banal, donc fréquent (débit), et identique à chaque fois (stabilité).
- **Tests automatisés** : les erreurs sont détectées avant la production (stabilité), sans attendre une phase de recette manuelle (débit).
- **Monitoring / observabilité** : un incident est repéré et compris vite (temps de restauration).
- **Approbation par un comité externe (CAB)** : contre-exemple. Elle ralentit le débit **sans** améliorer la stabilité.

> [!note] Note
> C'est ce qui explique le message clé des métriques : débit et stabilité progressent ensemble parce qu'ils dépendent **des mêmes pratiques**.

## Le catalogue complet

<iframe src="https://dora.dev/capabilities/" width="100%" height="600px"></iframe>


<style>
iframe {
  border: 1px solid #f1f1f1;
}
</style>
