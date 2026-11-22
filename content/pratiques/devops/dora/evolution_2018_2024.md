+++
title = "Évolution 2018-2025"
description = "Ce qui a changé dans le framework DORA entre le livre Accelerate de 2018 et le rapport 2025 : métriques renommées, fiabilité, passage à l'instabilité et rework rate."
weight = 20
+++

> [!ressource] Ressources
> - [Framework DORA 2024 : les évolutions depuis le livre Accelerate 2018](https://youtu.be/H8H1cGtzZ4s)
> - [State of AI-assisted Software Development 2025 - DORA (PDF)](https://services.google.com/fh/files/misc/2025_state_of_ai_assisted_software_development.pdf)

## En un coup d'œil

| | Accelerate (2018) | 2024 | 2025 |
| --- | --- | --- | --- |
| **Axes** | Débit / Stabilité | Débit / Stabilité | Débit / **Instabilité** |
| **Métriques** | 4 | 4 + fiabilité | 5 |
| **Nouveauté** | — | Reliability | Rework rate |

## Évolution du Core DORA

- **2018** : Accelerate présente 24 capacités, regroupées en techniques, processus, management et culture, qui expliquent la performance de livraison.
- **Aujourd'hui** : le [DORA Core]({{< relref "dora_core/index" >}}) garde la même logique (capacités → métriques → résultats) mais ne conserve que les résultats les mieux établis. Les résultats visés s'élargissent : au-delà de la performance de l'organisation, le bien-être des équipes devient un résultat à part entière.

## Évolution des métriques

| Accelerate (2018) | Nom actuel | Ce qui change |
| --- | --- | --- |
| Deployment Frequency | Deployment frequency | Rien |
| Delivery Lead Time | Change lead time / Lead time for changes | Renommage |
| Change Fail Percentage | Change fail rate | Renommage |
| Mean Time To Restore (MTTR) | Failed Deployment Recovery Time (FDRT) | Le périmètre se réduit |
| — | Reliability | Ajout |
| — | Rework rate | Ajout (2025) |

### MTTR → FDRT

- Le MTTR était global : il incluait toutes les causes d'incidents (bugs, problème d'infrastructure).
- FDRT se concentre sur la capacité d'une équipe à gérer les échecs de ses déploiements, et sur le temps qu'il lui faut pour revenir dans un état stable.

### Reliability

Définir des objectifs de service pour garantir :
- que le système reste performant ;
- l’alignement avec les attentes des utilisateurs.

Les quatre premières métriques permettent de mesurer l'efficacité du processus de livraison mais pas réellement la performance du service en question.

### 2025 : de la stabilité à l'instabilité

- Les métriques sont rangées en **débit** et **instabilité** : pour l'instabilité, plus le chiffre est haut, plus c'est mauvais.
- Le temps de restauration (FDRT) passe du côté du débit.
- Le *rework rate* mesure la part des déploiements non planifiés, faits pour corriger un incident.

Détail des cinq métriques : [Métriques]({{< relref "dora_core/metriques" >}}).
