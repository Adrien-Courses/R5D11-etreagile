+++
title = "Team Topologies"
description = "Notes de lecture de Team Topologies, sur les quatre types d'équipes et les trois modes d'interaction."
weight = 30
+++

<img src="https://m.media-amazon.com/images/I/71rps7F0FuL.jpg" width="300">
<br>

> [!Ressource] Ressources
> - https://teamtopologies.com/
> - https://techblog.deepki.com/team_topologies/

## Introduction

*Team Topologies* part d'une question simple : comment organiser les équipes d'une entreprise pour qu'elles puissent répondre facilement aux changements ? Pour les auteurs, rapidité et sécurité ne sont pas incompatibles, à condition de placer les équipes et les personnes au centre de l'organisation.

> The good news is that it is possible to be fast and safe with the right mindset and with tools that emphasize adaptability as well as repeatability, while putting teams and people at the center. As Mark Schwartz and co-authors put it in their 2016 paper Thinking Environments, “the organizational structure must coordinate accountabilities to support the goals of delivering high-quality, impactful software.” (page 4)

Pour y parvenir, le livre propose un vocabulaire commun : quatre types d'équipes, trois modes d'interaction entre elles, et des repères concrets pour dimensionner l'organisation selon sa taille. Ces outils s'appuient sur trois notions transverses : la loi de Conway, la charge cognitive des équipes et la capacité de l'organisation à percevoir les signaux de son environnement (*sensing organization*).

> Team Topologies provides four fundamental team types—stream-aligned, platform, enabling, and complicated-subsystem—and three core team interaction modes—collaboration, X-as-a-Service, and facilitating. Together with awareness of Conway’s law, team cognitive load, and how to become a sensing organization, Team Topologies results in an effective and humanistic approach to building and running software systems.

## Retour sur la loi de Conway

La loi de Conway est présentée en détail sur la [page qui lui est consacrée]({{< relref "equipe_agile/constitution_equipe/conway_law" >}}). Rappelons simplement qu'elle établit un lien entre la structure de communication d'une organisation et l'architecture des systèmes qu'elle produit. Les auteurs la complètent par une formule de Ruth Malan, qui souligne lequel des deux l'emporte en cas de désaccord :

> If the architecture of the system and the architecture of the organization are at odds, the architecture of the organization wins. (page 17)

### Quelles conséquences pour l'organisation ?

Dans le chapitre 2, les auteurs tirent de cette loi plusieurs principes de conception organisationnelle.

- **Organization design requires technical expertise** Si les managers décident seuls de la structure des équipes, ils décident implicitement de l'architecture du logiciel. Les profils techniques doivent donc être associés à la conception de l'organisation.
- **Everyone does not need to communicate with everyone.** Une organisation où chacun échange avec tout le monde produit une architecture fortement couplée, de type monolithe.
- **Restrict unnecessary communication.** Les communications entre deux équipes doivent rester limitées. Si deux équipes ont constamment besoin l'une de l'autre, c'est probablement qu'elles devraient n'en former qu'une.

Les auteurs résument la portée de la loi en deux effets (page 29) :

> The effects of this simple law are far reaching.
> - On one hand, the organization’s design limits the number of possible solutions for a given system’s architecture.
> - On the other hand, the speed of software delivery is strongly affected by how many team dependencies the organization design instills.

Le premier effet signifie que, parmi toutes les architectures possibles pour un système, l'organisation n'en explore réellement qu'une partie : celle qui est compatible avec la manière dont ses membres collaborent.

Le second effet porte sur les dépendances. Chaque fois qu'une équipe doit attendre une autre équipe pour avancer (une validation, une modification d'API, un déploiement coordonné, un ticket auprès de l'équipe infrastructure), elle subit une dépendance. Chacune ajoute du temps d'attente, de la coordination, des réunions et des files d'attente. À l'inverse, des équipes découpées par flux de valeur, c'est-à-dire responsables d'un produit ou d'un domaine de bout en bout, peuvent livrer sans dépendre des autres. C'est l'argument central de *Team Topologies* : **concevoir l'organisation pour réduire au minimum les dépendances bloquantes**.

Les auteurs nuancent toutefois ce principe : la collaboration reste nécessaire lorsqu'il faut explorer un sujet nouveau, mais elle devient un coût inutile lorsque le travail relève de l'exécution.

> Fast flow requires restricting communication between teams. Team collaboration is important for gray areas of development, where discovery and expertise is needed to make progress. But in areas where execution prevails—not discovery—communication becomes an unnecessary overhead.

### Utiliser la loi à son avantage

Puisque la structure des équipes influence l'architecture, on peut inverser le raisonnement : définir d'abord l'architecture souhaitée, puis organiser les équipes en conséquence. C'est la [manœuvre de Conway inversée]({{< relref "equipe_agile/constitution_equipe/conway_law#inverse-conways-law" >}}). Dans l'exemple donné par les auteurs, une organisation évite une base de données monolithique en intégrant des compétences de base de données dans l'équipe applicative, qui gagne ainsi l'autonomie nécessaire pour gérer son propre stockage.

> One key approach to achieving the software architecture (and associated benefits like speed of delivery or time to recover from failure) is to apply the reverse Conway maneuver: designing teams to match the desired architecture. We provided a simple example where an organization could avoid a monolithic database by embedding database skills in the application team, so that they had sufficient autonomy to maintain a separate data store (perhaps relying on a centralized DBA team for recommendations on database design or synchronization with other databases).

En somme, la loi de Conway n'est pas une contrainte à subir mais une force à exploiter : architecture logicielle et organisation des équipes tendent à converger, autant choisir la direction de cette convergence.

> In short, by considering the impact of Conway’s law when designing software architectures and/or reorganizing team structures, you will be able to take advantage of the isomorphic force at play, which converges the software architecture and the team design.
