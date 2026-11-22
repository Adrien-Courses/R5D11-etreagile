+++
title = "L'IA et le côté humain d'Agile"
description = "Agile est « people-oriented » selon Martin Fowler. L'IA renforce-t-elle ou affaiblit-elle cette dimension : interactions, apprentissage, responsabilité ?"
weight = 50
+++

> [!ressource] Ressources
> - [The New Methodology - Martin Fowler (2005)](https://martinfowler.com/articles/newMethodology.html)
> - [The Learning Loop and LLMs - Unmesh Joshi (2025)](https://martinfowler.com/articles/llm-learning-loop.html)
> - [Humans and Agents in Software Engineering Loops - Kief Morris (2026)](https://martinfowler.com/articles/exploring-gen-ai/humans-and-agents.html)
> - [Do We Need to Rewrite Scrum in the Age of AI? - Krystian Kaczor, scrum.org (2025)](https://www.scrum.org/resources/blog/do-we-need-rewrite-scrum-age-ai)
> - [How AI will change software engineering – with Martin Fowler - The Pragmatic Engineer (2025)](https://youtu.be/CQmI4XKTa0U) — dont un passage sur les conseils aux juniors (1:37:44)

L'agilité ne se résume pas à des itérations et des pratiques techniques. Le cours le dit dans [Dimension humaine]({{< relref "equipe_agile/dimension_humaine" >}}) :

> L'importance des gens, le côté humain c'est le principal différenciateur de la philosophie Agile.

Cette page se demande si l'IA renforce ce côté humain ou l'affaiblit. Elle part de ce que Martin Fowler entendait par là, puis regarde trois choses : les interactions dans l'équipe, l'apprentissage, et la responsabilité.

## Ce que Fowler appelait « people-oriented »

En 2005, dans *The New Methodology*, Fowler résume ce qui distingue les méthodes agiles des méthodes classiques en deux phrases :

> Agile methods are adaptive rather than predictive. [^1]

> Agile methods are people-oriented rather than process-oriented. [^1]

Le cours a beaucoup travaillé la première (voir [Encaisser l'incertitude]({{< relref "philosophie/pourquoi_agile/encaisser_incertitude/index" >}})). La seconde mérite qu'on s'y arrête.

Fowler explique ce qu'il reproche aux méthodes classiques dans une section intitulée *Plug-Compatible Programming Units*, c'est-à-dire des unités de programmation interchangeables :

> One of the aims of traditional methodologies is to develop a process where the people involved are replaceable parts. [^1]

Dans cette vision, on a un analyste, des développeurs, des testeurs ; peu importe lesquels. « The individuals aren't so important, only the roles are important. » Les méthodes agiles rejettent cette idée. Fowler s'appuie sur Alistair Cockburn : un processus prévisible a besoin de composants prévisibles, or « people are not predictable components ». Il décrit aussi l'effet pervers de la vision classique :

> If you expect all your developers to be plug-compatible programming units, you don't try to treat them as individuals. This lowers morale (and productivity). [^1]

### L'agent, l'unité interchangeable enfin trouvée ?

C'est ici que l'IA pose une question inconfortable. Un agent de code ressemble beaucoup à ce que les méthodes classiques cherchaient : une ressource qu'on remplace par une autre (Claude, Codex…), qu'on lance à la demande, qui ne se fatigue pas et ne démissionne pas.

L'argument de Fowler tombe-t-il pour autant ? Non, parce qu'il ne portait pas sur la production du code. Il portait sur la nature du travail : développer un logiciel est un travail créatif, où l'on découvre ce qu'il faut construire en le construisant. Unmesh Joshi le rappelle dans un article publié sur le site de Fowler :

> Software development has always resisted the idea that it can be turned into an assembly line. [^2]

Et il ajoute, en titre de section : « LLMs are reintroducing the assembly line metaphor ». Les LLM réintroduisent l'image de la chaîne de montage, celle que l'agilité avait combattue.

=> L'IA ne réfute pas Fowler. Elle rend de nouveau tentante la vision qu'il critiquait.

## Les interactions : libérées ou remplacées ?

Le Manifeste fait passer « les individus et leurs interactions » en premier. Le cours donne la raison dans [le Manifeste]({{< relref "philosophie/philosophie_agile/definir_agile/manifeste" >}}) :

> La communication orale lève rapidement les ambiguïtés et transmet la « connaissance tacite » difficile à formaliser par écrit.

La connaissance tacite, c'est ce que l'on sait sans l'avoir jamais écrit : pourquoi telle règle métier existe, ce que tel client veut vraiment dire, quelle partie du code est fragile. Elle circule en parlant. Un ingénieur de Canon, cité dans [Caractéristiques d'une bonne équipe]({{< relref "equipe_agile/constitution_equipe/index" >}}), décrit ce qui se passe quand l'équipe travaille dans la même pièce : « someone's information becomes yours, without even trying ».

Joshi rappelle que le développement est fait de ces échanges :

> Software creation involves constant interaction—between developers, product owners, users, and other stakeholders—each bringing their own insights. [^2]

L'IA peut jouer dans les deux sens.

- **Scénario optimiste** : l'agent prend en charge la frappe. Le temps libéré revient à la conversation, avec l'utilisateur et entre collègues.
- **Scénario pessimiste** : chacun dialogue avec son agent. On ne pose plus la question au collègue, on la pose à l'outil. C'est le mécanisme que le cours décrit pour le [télétravail]({{< relref "equipe_agile/modes_de_travail/teletravail" >}}) : moins d'échanges spontanés, et le risque d'avoir « des personnes qui s'enferment dans leur silo de connaissances/compétences ».

Dans le second scénario, l'agent ne reçoit pas non plus la connaissance tacite, puisqu'elle n'est écrite nulle part. C'est ce que la page [PRD, vision et US]({{< relref "ouvertures/agile_et_ia/spec_driven_development/prd_vision_us" >}}) appelait : « un agent ne participe à aucune conversation ».

=> Le scénario qui l'emporte n'est pas décidé par l'outil. Il dépend de ce que l'équipe fait du temps gagné.

## L'apprentissage : on ne court-circuite pas Shu Ha Ri

Le cours présente la maîtrise d'une pratique comme une progression en trois temps, [Shu Ha Ri]({{< relref "equipe_agile/roles_postures/shuhari" >}}) : d'abord reproduire, puis s'écarter, enfin inventer. Une progression « que l'on ne peut pas court-circuiter » (voir [Rôles et postures]({{< relref "equipe_agile/roles_postures/index" >}})).

Joshi décrit une boucle d'apprentissage proche [^2] : observer et comprendre, puis essayer soi-même, puis se souvenir et réappliquer dans un autre contexte. Sa conclusion porte sur l'IA :

> An AI can generate a perfect solution in seconds, but it cannot give you the experience you gain from the struggle of creating it yourself. [^2]

> The small failures and the "aha!" moments are essential features of learning, not bugs to be automated away. [^2]

Il fait aussi le lien avec les pratiques agiles. Selon lui, les itérations, le binôme, les rétrospectives ou le TDD ne sont pas des rituels :

> It's because these techniques acknowledge this fundamental nature of learning and its importance in the work we do. [^2]

### Aptitudes et attitudes

Le cours fournit une distinction utile, dans [Aptitudes et attitudes]({{< relref "pratiques/software_craftsmanship/attitudes_et_aptitudes" >}}). Les **aptitudes** sont ce qu'on sait faire : programmer, connaître un langage, un framework. Les **attitudes** sont la façon de s'y prendre : commencer par le but, avancer à petits pas, chercher le feedback rapide, rechercher la simplicité. Et le craft est défini comme « un ensemble d'attitudes ».

L'IA prend en charge une partie des aptitudes : elle écrit du code dans un langage qu'on connaît mal. Les attitudes restent humaines. Mais elles s'apprennent en pratiquant, et c'est justement la pratique que l'IA retire.

=> La question reste ouverte : comment un junior acquiert-il les attitudes du craft s'il n'écrit plus le code lui-même ?

### Ce que la vitesse cache

Joshi met en garde contre une vitesse qui ne dure pas. Sans apprentissage, le gain du départ disparaît dès que le besoin s'écarte de ce que l'outil sait faire. Il parle de *Maintenance Cliff*, une falaise de maintenance :

> LLMs represent the ultimate version of the Maintenance Cliff: a tempting shortcut that bypasses the essential learning required to build robust, maintainable systems for the long term. [^2]

Le cours dit la même chose avec d'autres mots, dans [Comment augmenter la productivité]({{< relref "regard_critique/mesurer_productivite/comment_ameliorer_productiviter" >}}) : la santé du code et la connaissance partagée sont « des stocks et non des débits ». Une équipe peut livrer régulièrement pendant des mois tout en vidant son stock de compréhension. Les métriques de livraison ne le voient pas.

## Qui assume ?

Fowler défend dans le même essai que les développeurs sont des professionnels responsables :

> As such they are the best people to decide how to conduct their technical work. [^1]

Quand l'agent écrit le code, que reste-t-il de cette responsabilité ? Kief Morris propose une réponse [^3]. Il distingue trois positions possibles pour l'humain : hors de la boucle (on laisse l'agent faire), dans la boucle (on vérifie chaque ligne, et l'on devient le goulot), ou **sur** la boucle :

> The right place for us humans is to build and manage the working loop rather than either leaving the agents to it or micromanaging what they produce. Let's call this "on the loop." [^3]

Être sur la boucle, c'est décider des tests, des règles, des consignes qui encadrent l'agent, et les améliorer quand le résultat ne convient pas. Le développeur reste responsable, mais de la façon dont le code est produit plutôt que de chaque ligne.

Le Lean a un précédent. Le [Jidoka]({{< relref "philosophie/philosophie_lean/toyota_production_system/jidoka" >}}) signifie « automatisation avec une touche d'humain » : la machine s'arrête d'elle-même à la première anomalie, et c'est un humain qui comprend le problème et décide. Le cours ajoute une mise en garde qui s'applique telle quelle à l'IA : « Les managers obsédés par l'excellence opérationnelle s'imaginent que le but de l'automatisation est d'éliminer les coûts liés aux « ressources humaines » ».

=> Un test qui échoue arrête l'agent. Décider quoi faire ensuite reste un travail humain.

## Motivation

Reste une question plus simple : relire du code généré toute la journée, est-ce encore un métier qu'on a envie de faire ? Le cours parle de « dette de motivation » dans [Développeurs VS Exécutants]({{< relref "equipe_agile/roles_postures/developpeur_executant/index" >}}). Le risque est que le développeur exécutant devienne un relecteur exécutant.

Les premières données sont moins sombres. Le rapport DORA 2025 associe l'adoption de l'IA à plus de temps passé sur un travail jugé utile, et à plus de fierté : « higher AI adoption is associated with greater levels of authentic pride » [^4]. Il ne trouve en revanche aucun effet sur l'épuisement, ni dans un sens ni dans l'autre [^5].

Et certaines choses ne se délèguent pas. Kaczor le dit à propos du Scrum Master :

> An AI cannot read the room during a tense retrospective, sense a developer's burnout [^6]

> [!affirmation] Affirmation
> L'IA ne rend pas l'agilité moins humaine par elle-même. Elle retire une partie du travail qui obligeait les gens à se parler et à apprendre ensemble. Si l'équipe ne réinvestit pas ce temps dans les interactions et l'apprentissage, l'agent devient l'unité interchangeable que Fowler critiquait, et les développeurs risquent de le devenir avec lui.

[^1]: Martin Fowler, [The New Methodology](https://martinfowler.com/articles/newMethodology.html) (version révisée de 2005)
[^2]: Unmesh Joshi, [The Learning Loop and LLMs](https://martinfowler.com/articles/llm-learning-loop.html), martinfowler.com (2025)
[^3]: Kief Morris, [Humans and Agents in Software Engineering Loops](https://martinfowler.com/articles/exploring-gen-ai/humans-and-agents.html), martinfowler.com (2026)
[^4]: DORA, [State of AI-assisted Software Development 2025](https://services.google.com/fh/files/misc/2025_state_of_ai_assisted_software_development.pdf), p. 45
[^5]: *Ibid.*, p. 39
[^6]: Krystian Kaczor, [Do We Need to Rewrite Scrum in the Age of AI?](https://www.scrum.org/resources/blog/do-we-need-rewrite-scrum-age-ai), scrum.org (2025)
