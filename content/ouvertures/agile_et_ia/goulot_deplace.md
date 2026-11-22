+++
title = "L'IA déplace le goulot"
description = "Si l'IA accélère l'écriture du code, où va le délai ? Relecture par le flux : files d'attente, WIP, contrainte du système."
weight = 10
+++

> [!ressource] Ressources
> - [AI Made Engineering Faster. Why Didn't Value Follow? - Yuval Yeret (2026)](https://yuvalyeret.com/blog/ai-coding-moved-the-bottleneck/)
> - [AI Didn't Kill Agile. It Moved the Bottleneck. - Yuval Yeret (2026)](https://yuvalyeret.com/blog/ai-didnt-kill-agile-it-moved-the-bottleneck/)
> - [Does AI Make the Agile Manifesto Obsolete? - InfoQ (2026)](https://www.infoq.com/news/2026/02/ai-agile-manifesto-debate/)
> - [Humans and Agents in Software Engineering Loops - Kief Morris (2026)](https://martinfowler.com/articles/exploring-gen-ai/humans-and-agents.html)
> - [Announcing the 2025 DORA Report - Nathen Harvey, Derek DeBellis (2025)](https://cloud.google.com/blog/products/ai-machine-learning/announcing-the-2025-dora-report)
> - Le But - Eliyahu Goldratt (1984)

Un agent de code écrit en quelques minutes ce qui prenait une journée. On en déduit souvent que le logiciel sera livré plus vite. Ce n'est vrai que si l'écriture du code était ce qui ralentissait la livraison.

Cette page reprend les outils du [Lean]({{< relref "philosophie/philosophie_lean/index" >}}) pour poser la question autrement : quand une étape accélère, où va le délai ?

## Le code était-il le goulot ?

La [Value Stream Map]({{< relref "philosophie/philosophie_lean/value_stream_map" >}}) distingue deux durées : le temps pendant lequel quelqu'un travaille sur une demande, et le temps total qu'elle met à sortir. Sur une chaîne de livraison non optimisée, le premier représente 5 à 15 % du second. Le reste est de l'attente : une validation, une relecture, un environnement de test, une date de mise en production.

Nous en avions tiré une conséquence, écrite avant qu'il soit question d'IA :

> Diviser par deux le temps de développement d'une fonctionnalité qui met trois mois à sortir ne fait gagner que quelques jours.

Refaisons le calcul avec un agent. Les chiffres ci-dessous sont illustratifs, construits sur l'ordre de grandeur de la page VSM : 90 jours de bout en bout, dont 9 jours de travail effectif.

| | Avant | Développement divisé par 2 | Développement divisé par 10 |
| --- | --- | --- | --- |
| Développement | 5 j | 2,5 j | 0,5 j |
| Autres travaux (cadrage, recette, déploiement) | 4 j | 4 j | 4 j |
| Attentes entre les étapes | 81 j | 81 j | 81 j |
| **Délai total** | **90 j** | **87,5 j** | **85,5 j** |

Un développement dix fois plus rapide raccourcit le délai de 5 %. L'équipe a réellement gagné du temps, mais le client ne le voit pas.

C'est ce que nous disions du principe [livrer aussi vite que possible]({{< relref "philosophie/philosophie_lean/lean_software_development/les_six_autres" >}}) : « Le levier n'est presque jamais la vitesse de frappe des développeurs : c'est le temps passé en file d'attente. » L'IA augmente la vitesse de frappe. Elle ne touche pas aux files.

> [!affirmation] Affirmation
> L'IA accélère une étape. Le délai de livraison dépend du système entier.


## Ce que dit la théorie des contraintes

Eliyahu Goldratt a formalisé cette idée dans *Le But* (1984). Tout système a une contrainte, l'étape qui limite le débit de l'ensemble. Deux conséquences en découlent :

- une heure gagnée sur la contrainte est une heure gagnée pour tout le système ;
- une heure gagnée ailleurs ne change rien au débit. Elle produit seulement du travail qui attendra devant la contrainte.

Goldratt en tire une démarche en cinq étapes : identifier la contrainte, l'exploiter au mieux, subordonner le reste du système à son rythme, augmenter sa capacité, puis recommencer, parce que la contrainte s'est déplacée.

Appliquée à notre sujet, la démarche pose une question simple : le développement était-il la contrainte ? Le cours a déjà répondu, dans [Lean vs Agile]({{< relref "philosophie/philosophie_lean/lean_vs_agile" >}}), à propos de l'agilité elle-même :

> The expected organizational benefits of agile often failed to materialize because agile focused on optimizing software development, which frequently was not the system constraint.

L'IA risque de reproduire la même erreur, en plus grand : **optimiser encore le développement, là où il ne limitait déjà pas le système.**

## Où va le goulot ?

Yuval Yeret décrit les deux cas possibles quand l'ingénierie cesse d'être la contrainte :

> You can 10x engineering, but if engineering is no longer the constraint, that output will create congestion downstream. [^1]

> Or it may create an environment where engineering is starved, because it does not have enough well-shaped work to pull. [^1]

=> Le goulot peut donc partir vers l'aval ou vers l'amont.

### En aval : relire, tester, déployer

C'est le cas le plus visible. Nous l'avions décrit à propos de l'[optimisation locale]({{< relref "philosophie/philosophie_lean/lean_software_development/les_six_autres" >}}) où une équipe de développement à pleine capacité produit plus de code, donc allonge la file d'attente de la recette.

Avec un agent, la file se forme d'abord devant la relecture. Le code arrive plus vite que les personnes capables de le relire. Kief Morris note que relire chaque ligne produite par un agent fait de l'humain le goulot [^2]. La page [Specification Driven Development]({{< relref "ouvertures/agile_et_ia/spec_driven_development/index" >}}) arrivait à la même conclusion : **ce qui devient cher, ce n'est plus d'écrire, c'est de vérifier et d'assumer.**

Le rapport DORA 2025 donne un indice dans le même sens. L'adoption de l'IA y est associée à un meilleur débit de livraison, mais

> AI adoption does continue to have a negative relationship with software delivery stability. [^3]

On livre plus, et ce qui est livré casse plus souvent. C'est ce qu'on attend d'un système où l'étape de vérification est débordée.

### En amont : savoir quoi construire

Le second cas est moins intuitif. L'équipe va si vite qu'elle manque de travail bien défini. Le backlog se vide plus vite que le [Product Owner]({{< relref "frameworks/framework_scrum/responsabilites/product_owner" >}}) ne peut le remplir avec des besoins compris et priorisés. L'IA aide beaucoup à coder, parce que le code se vérifie : on peut essayer plusieurs fois et constater si cela fonctionne. Elle aide moins sur le reste

> It is harder to get AI to help with product discovery or product adoption. [^1]

Sonya Siderova résume la situation dans le débat rapporté par InfoQ

> Agile isn't dead. It's optimizing a constraint that moved. [^4]


## Le code généré est un stock

Le [juste-à-temps]({{< relref "philosophie/philosophie_lean/toyota_production_system/just_in_time" >}}) oppose deux façons de produire. En flux poussé, chaque étape produit à son rythme maximal et pousse le résultat vers la suivante. En flux tiré, rien n'est produit tant que l'aval n'en a pas besoin.

Un agent de code est une machine à flux poussé. Il ne se fatigue pas, il ne coûte presque rien à relancer, et rien ne l'empêche de produire dix fonctionnalités pendant que l'équipe en relit une. Le résultat est connu : le travail s'entasse entre les postes.

Nous avions listé les formes que prend ce stock dans une équipe logicielle : spécifications écrites et pas encore développées, code écrit et pas encore intégré, fonctionnalités terminées et pas encore en production, tickets en attente de revue. Et nous avions ajouté que ce stock est « du travail déjà payé qui ne rapporte encore rien, et qui se périme ».

Le code généré se périme comme les autres. Une branche qui attend trois semaines sa relecture doit être réalignée sur le reste du code. Celui qui l'a demandée a oublié le contexte. Le besoin a pu changer entre-temps.

> [!danger] Bon marché à produire ne veut pas dire gratuit à garder : coût de maintenance
> Le coût d'une ligne générée est faible au moment où elle est écrite. Il réapparaît ensuite : il faut la relire, la tester, l'intégrer, la maintenir. Produire plus que ce que l'aval peut absorber ne fait que déplacer la facture.

## Conserver des pratiques

**Limiter le travail en cours.** La [limite de WIP]({{< relref "frameworks/framework_kanban/principes" >}}) est un mécanisme de flux tiré : on ne démarre une tâche que si une place se libère en aval. Avec un agent, la limite utile ne porte plus sur la colonne « en développement », qui ne sature jamais. Elle porte sur « à relire » et « à valider ». Quand ces colonnes sont pleines, on arrête de générer.

**Garder des lots petits.** Un agent peut produire deux mille lignes d'un coup. Personne ne peut les relire sérieusement. Un petit lot traverse la chaîne plus vite, échoue moins cher et se corrige plus tôt. Si la file se forme devant la relecture, c'est la relecture qu'il faut outiller : tests automatisés, lots plus petits, critères d'acceptation exécutables.


> [!affirmation] Affirmation
> L'IA ne supprime pas le goulot, elle le déplace hors du développement. Le travail de l'équipe consiste à le retrouver.


[^1]: Yuval Yeret, [AI Made Engineering Faster. Why Didn't Value Follow?](https://yuvalyeret.com/blog/ai-coding-moved-the-bottleneck/) (2026)
[^2]: Kief Morris, [Humans and Agents in Software Engineering Loops](https://martinfowler.com/articles/exploring-gen-ai/humans-and-agents.html) (2026)
[^3]: Nathen Harvey et Derek DeBellis, [Announcing the 2025 DORA Report](https://cloud.google.com/blog/products/ai-machine-learning/announcing-the-2025-dora-report) (2025)
[^4]: Sonya Siderova, citée dans [Does AI Make the Agile Manifesto Obsolete?](https://www.infoq.com/news/2026/02/ai-agile-manifesto-debate/), InfoQ (2026)
[^5]: Yuval Yeret, [AI Didn't Kill Agile. It Moved the Bottleneck.](https://yuvalyeret.com/blog/ai-didnt-kill-agile-it-moved-the-bottleneck/) (2026)
