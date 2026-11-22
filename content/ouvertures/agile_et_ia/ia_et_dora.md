+++
title = "IA et métriques DORA"
description = "L'IA améliore le débit mais dégrade la stabilité : ce que dit le rapport DORA 2025, et ce que les pratiques agiles y changent."
weight = 20
+++

> [!ressource] Ressources
> - [State of AI-assisted Software Development 2025 - DORA (rapport complet, PDF)](https://services.google.com/fh/files/misc/2025_state_of_ai_assisted_software_development.pdf)
> - [Announcing the 2025 DORA Report - Nathen Harvey, Derek DeBellis (2025)](https://cloud.google.com/blog/products/ai-machine-learning/announcing-the-2025-dora-report)
> - Accelerate - Nicole Forsgren, Jez Humble, Gene Kim (2018)

Le cours défend une idée tirée d'[Accelerate]({{< relref "pratiques/devops/accelerate/index" >}}) : la vitesse et la stabilité ne s'échangent pas, elles progressent ensemble. La page [Produit de haute qualité]({{< relref "philosophie/pourquoi_agile/produit_haute_qualite/index" >}}) le dit ainsi :

> L'arbitrage « on peut avoir vite ou bien, choisissez » n'est pas une loi de la nature. C'est le symptôme d'un système de livraison mal outillé.

Le rapport DORA 2025, consacré à l'IA, semble dire le contraire : les équipes qui utilisent davantage l'IA livrent plus vite, mais leurs livraisons cassent plus souvent. Cette page regarde ce que le rapport mesure, ce qu'il trouve, et ce que cela dit des pratiques agiles.

## Ce que mesure DORA en 2025

Les quatre métriques d'Accelerate ont [évolué depuis 2018]({{< relref "pratiques/devops/dora/evolution_2018_2024" >}}). Le rapport 2025 en utilise cinq, rangées en deux familles [^1] :

| Famille | Métrique | Ce qu'elle mesure |
| --- | --- | --- |
| **Débit** | Lead time for changes | Le temps entre le commit et la mise en production |
| | Deployment frequency | Le nombre de déploiements sur une période |
| | Failed deployment recovery time | Le temps pour se remettre d'un déploiement raté |
| **Instabilité** | Change fail rate | La part des déploiements qui demandent une intervention immédiate (rollback, hotfix) |
| | Rework rate | La part des déploiements non planifiés, faits à cause d'un incident en production |

Deux différences avec Accelerate :

- on parle d'**instabilité** et non plus de stabilité : plus le chiffre est haut, plus c'est mauvais ;
- le temps de restauration est rangé du côté du débit, et une nouvelle métrique, le *rework rate*, compte le travail imprévu causé par les incidents.


## Ce que dit le rapport sur l'IA

En 2024, le constat de DORA était négatif sur les deux plans. Pour chaque hausse de 25 % de l'adoption de l'IA, il estimait une baisse de 1,5 % du débit et une hausse de 7,2 % de l'instabilité [^4].

En 2025, le débit s'est retourné. L'instabilité, non :

> AI adoption now improves software delivery throughput, a key shift from last year. However, it still increases delivery instability. This suggests that while teams are adapting for speed, their underlying systems have not yet evolved to safely manage AI-accelerated development. [^2]

Le rapport explique le retournement du débit par l'apprentissage : les outils se sont améliorés, et les équipes ont appris où l'IA leur est utile. Il reconnaît en revanche ne pas savoir pourquoi l'instabilité n'a pas suivi le même chemin [^5].

### « Ce n'est pas grave si on corrige vite »

C'est l'objection naturelle : si l'IA permet de réparer aussi vite qu'elle casse, l'instabilité serait un prix acceptable. Le rapport a testé l'hypothèse, en cherchant si l'adoption de l'IA atténuait les effets négatifs habituels de l'instabilité :

> We found no evidence of such a moderating effect. On the contrary, instability still has significant detrimental effects on crucial outcomes like product performance and burnout, which can ultimately negate any perceived gains in throughput. [^6]

=> Livrer vite des changements qui cassent ne vaut pas livrer vite des changements qui tiennent. L'instabilité continue de coûter en qualité du produit et en épuisement des équipes.

### Une contradiction avec Accelerate ?

Accelerate n'a jamais dit que la vitesse produisait la stabilité. Il a montré que les deux progressaient ensemble **chez les équipes qui avaient certaines pratiques** : intégration continue, architecture faiblement couplée, lots de petite taille. Le cours le résume par « Team Experiment + Small Batches + Work Visible ».

Or l'IA agit précisément sur la taille des lots. Un agent produit en une fois ce qu'un développeur écrivait en plusieurs jours. Le rapport en fait lui-même l'hypothèse :

> AI use is also associated with a higher degree of software instability. We have hypothesized that this is likely, in part, because it is harder to review larger batches of code. [^7]

On retrouve le goulot décrit dans [L'IA déplace le goulot]({{< relref "ouvertures/agile_et_ia/goulot_deplace" >}}) : le code arrive plus vite que la capacité à le relire.

Le rapport ajoute une observation qui va dans le même sens :

> As of now, AI tends to turn up at the keyboard, which can help explain why code quality and productivity benefit, but friction, burnout, and instability may not. [^8]

L'IA améliore ce qui se passe au clavier. L'instabilité dépend de ce qui se passe ensuite : relecture, tests, déploiement, coordination entre équipes.

> [!affirmation] Affirmation
> L'IA ne réfute pas Accelerate. Elle réintroduit l'arbitrage vitesse/stabilité là où elle fait grossir les lots. C'est exactement le « système de livraison mal outillé » dont parle le cours.

## L'IA amplifie ce qui existe déjà

C'est le constat central du rapport, posé dès sa première page :

> AI's primary role in software development is that of an amplifier. It magnifies the strengths of high-performing organizations and the dysfunctions of struggling ones. [^2]

Un amplificateur ne crée pas le son : il rend plus fort ce qu'on lui donne. L'IA fait pareil. Une équipe qui travaille bien travaille encore mieux. Une équipe qui a des problèmes les voit grossir.

### Comment DORA le sait

DORA ne s'est pas contenté de demander « l'IA aide-t-elle ? ». Il a posé une question plus utile : **dans quelles équipes l'IA aide-t-elle le plus ?**

Pour y répondre, il a choisi quinze pratiques et comparé les équipes qui les appliquent avec celles qui ne les appliquent pas. Pour sept d'entre elles, la différence est nette : quand l'équipe applique la pratique, l'IA lui apporte davantage [^9].

| Pratique | En clair | Dans le cours |
| --- | --- | --- |
| Une position claire sur l'IA (*clear and communicated AI stance*) | L'entreprise dit quels outils sont permis et encourage à les essayer | — |
| Des données internes saines (*healthy data ecosystems*) | Les données de l'entreprise sont fiables, accessibles et pas éparpillées | — |
| Des données accessibles à l'IA (*AI-accessible internal data*) | L'outil d'IA peut lire la documentation et le code de l'entreprise | — |
| Une plateforme interne de qualité (*quality internal platforms*) | Des outils communs à toutes les équipes, pour tester et déployer | — |
| Une bonne gestion de versions (*strong version control practices*) | Des commits fréquents, un retour arrière facile | [Intégration continue]({{< relref "frameworks/framework_xp/pratiques" >}}) |
| **Travailler en petits lots** (*working in small batches*) | Découper en petits changements, livrés souvent | [Lean]({{< relref "philosophie/philosophie_lean/lean_software_development/les_six_autres" >}}), XP, Accelerate |
| **Être centré sur l'utilisateur** (*user-centric focus*) | Faire passer le besoin de l'utilisateur avant tout | [User-centric]({{< relref "philosophie/pourquoi_agile/user_centric" >}}) |

Les deux dernières sont des pratiques agiles bien plus anciennes que l'IA. Regardons ce que le rapport en dit.

### Les petits lots

DORA mesure la taille des lots par trois questions : combien de lignes dans le dernier commit ? combien de changements regroupés dans une même livraison ? combien de temps pour finir une tâche [^10] ?

Le résultat se lit en deux temps. D'abord, chez les équipes qui travaillent en petits lots, l'IA apporte plus :

- **le produit est meilleur** : il aide mieux les utilisateurs dans leurs tâches, protège leurs données, répond plus vite (c'est ce que DORA appelle *product performance* [^3]) ;
- **le travail est moins pénible** : il y a moins de *friction*, c'est-à-dire moins d'obstacles qui gênent le travail au quotidien.

Ensuite, ces mêmes développeurs **se sentent moins productifs** avec l'IA que ceux qui travaillent en gros lots.

Le rapport l'explique ainsi : le sentiment de productivité que donne l'IA vient surtout du volume de code qu'elle produit d'un coup. Une équipe qui découpe finement profite moins de cet effet. Elle se sent donc moins productive, alors qu'elle livre un meilleur produit. Pour DORA, ce sentiment n'est pas ce qu'il faut viser :

> individual effectiveness should not necessarily be pursued as a goal in and of itself. [^10]

=> Avec l'IA, les petits lots donnent l'impression d'aller moins vite, mais ils donnent un meilleur produit. C'est le principe Lean d'[optimiser l'ensemble]({{< relref "philosophie/philosophie_lean/lean_software_development/les_six_autres" >}}) : ce qui compte est le résultat de toute la chaîne, pas le rendement ressenti par chacun.

### L'attention à l'utilisateur

DORA considère qu'une équipe est centrée sur l'utilisateur quand ses membres sont d'accord avec trois affirmations : notre priorité est de créer de la valeur pour les utilisateurs ; leur expérience passe avant tout ; s'occuper de l'utilisateur est la clé du succès de l'entreprise [^11].

Le résultat est très tranché :

- dans les équipes centrées sur l'utilisateur, l'IA améliore la performance de l'équipe ;
- dans les autres, l'IA la **dégrade**.

> Importantly, we also found that, in the absence of a user-centric focus, AI adoption has a negative impact on team performance. [^11]

L'IA fait aller plus vite. Une équipe qui sait pour qui elle travaille va plus vite dans la bonne direction. Une équipe qui ne le sait pas, dit le rapport, « may be moving quickly in the wrong direction » [^12].

### Visualiser le flux

Le rapport met en avant une troisième pratique, en dehors des sept : la cartographie du flux (*value stream management*). Elle consiste à dessiner le chemin d'une demande, de l'idée jusqu'à l'utilisateur, pour voir où elle attend. C'est la [Value Stream Map]({{< relref "philosophie/philosophie_lean/value_stream_map" >}}) du cours.

Selon DORA, l'IA seule a un effet modeste sur la performance de l'organisation. Chez celles qui cartographient leur flux, cet effet est beaucoup plus fort [^15]. Le rapport parle d'un « force multiplier » [^13].

La raison : la carte montre où l'IA sera utile. Le rapport donne un exemple. Une équipe découvre, en dessinant son flux, que la revue de code est son goulot. Au lieu d'utiliser l'IA pour écrire encore plus de code, qui s'entasserait devant la revue, elle l'utilise pour accélérer la revue elle-même [^14]. C'est le raisonnement de la page [L'IA déplace le goulot]({{< relref "ouvertures/agile_et_ia/goulot_deplace" >}}).

### Ce qu'il faut en retenir

> [!affirmation] Affirmation
> Les trois pratiques qui rendent l'IA utile (petits lots, attention à l'utilisateur, visualisation du flux) sont des pratiques agiles connues bien avant l'IA. Une équipe qui les applique profite de l'IA. Une équipe qui ne les applique pas accélère ses problèmes.

Le cours connaît déjà ce scénario sous le nom de [Flaccid Scrum]({{< relref "regard_critique/abandonner_agile/flaccid_scrum" >}}) : des équipes qui adoptent les réunions de Scrum sans les pratiques techniques, et dont le code devient au bout de quelques mois si difficile à modifier qu'elles ralentissent. Avec l'IA, le même manque risque de se voir plus tôt : plus de code, produit plus vite, dans une base que personne ne maîtrise.

## Ce que DORA ne mesure pas

Les cinq métriques mesurent la livraison, pas la valeur de ce qui est livré. Le cours le notait déjà : elles mesurent « l'efficacité du processus de livraison mais pas réellement la performance du service » ([Évolution 2018-2024]({{< relref "pratiques/devops/dora/evolution_2018_2024" >}})). Et *Modern Software Engineering*, cité dans [Mesurer la productivité ?]({{< relref "regard_critique/mesurer_productivite/index" >}}), rappelle que la stabilité « doesn't say anything about whether the team is building the right things ».

C'est pour cette raison que le rapport 2025 ne s'arrête pas aux cinq métriques. Il mesure aussi la performance du produit, la part du temps passée sur un travail jugé utile, la friction et l'épuisement [^3].

> [!danger] Mesurer ce que l'IA produit
> La tentation est de mesurer l'effet de l'IA par ce qu'elle produit : lignes de code, pull requests, tickets fermés. Ce sont exactement les métriques que le cours écarte : « Most metrics applied to software development are either irrelevant (velocity) or sometimes positively harmful (lines of code or test coverage). »
>
> L'IA fait exploser ces chiffres sans rien dire de la valeur créée. Voir [Output vs Outcome]({{< relref "philosophie/pourquoi_agile/produire_valeur/output_vs_outcome" >}}).

[^1]: DORA, [State of AI-assisted Software Development 2025](https://services.google.com/fh/files/misc/2025_state_of_ai_assisted_software_development.pdf)
[^15]: *Ibid.*, p. 77-78
