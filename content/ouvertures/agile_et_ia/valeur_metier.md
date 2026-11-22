+++
title = "L'IA trouve-t-elle la valeur métier ?"
description = "L'IA sait produire, pas juger. Ce qu'elle change à la découverte de la valeur : coût de l'expérience, prototypes, risque de construire la mauvaise chose plus vite."
weight = 60
+++

> [!ressource] Ressources
> - [AI makes Agile more alive - Jainish Shah, Thoughtworks (2026)](https://www.thoughtworks.com/insights/blog/agile-engineering-practices/ai-makes-agile-more-alive)
> - [Do We Need to Rewrite Scrum in the Age of AI? - Krystian Kaczor, scrum.org (2025)](https://www.scrum.org/resources/blog/do-we-need-rewrite-scrum-age-ai)
> - [AI Made Engineering Faster. Why Didn't Value Follow? - Yuval Yeret (2026)](https://yuvalyeret.com/blog/ai-coding-moved-the-bottleneck/)
> - [AI Didn't Kill Agile. It Moved the Bottleneck. - Yuval Yeret (2026)](https://yuvalyeret.com/blog/ai-didnt-kill-agile-it-moved-the-bottleneck/)
> - [State of AI-assisted Software Development 2025 - DORA (PDF)](https://services.google.com/fh/files/misc/2025_state_of_ai_assisted_software_development.pdf)

Un agent de code peut produire une fonctionnalité en quelques heures. Il ne peut pas dire si elle sert à quelque chose.

Cette page répond à la question du titre en quatre temps : ce qu'est la valeur, ce que l'IA change à sa recherche, le risque qu'elle introduit, et ce que cela fait au rôle du Product Owner.

## La valeur est un jugement

Le cours part d'une définition de Ron Jeffries, dans [Produire de la valeur]({{< relref "philosophie/pourquoi_agile/produire_valeur/index" >}}) :

> Choosing value is choosing what matters, to you.

Nous en avions tiré une conséquence : **la valeur n'est pas une propriété du logiciel, c'est un jugement porté par quelqu'un.** Et puisque c'est un jugement, on ne la connaît pas à l'avance. Elle est une **hypothèse**, que la livraison au client confirme ou infirme.

Posée ainsi, la question du titre a une réponse courte : **non**. L'IA n'est pas l'utilisateur. Elle ne vit pas son problème, elle ne se sert pas du produit, elle ne paie pas. Elle peut proposer une hypothèse de valeur ; seul l'usage réel peut la confirmer.

Ce que l'IA peut faire, c'est aider à formuler ces hypothèses. Krystian Kaczor le résume ainsi :

> AI tools can analyze customer feedback at scale and suggest feature priorities, but the Product Owner must still make the final calls on what delivers maximum value. [^1]

Elle peut aussi tromper. Dans [PRD, vision et US]({{< relref "ouvertures/agile_et_ia/spec_driven_development/prd_vision_us" >}}), nous avions vu qu'un LLM reproduit la **forme** d'une user story (*En tant que… je veux… afin de…*) sans sa **fonction**, qui est d'exprimer un bénéfice pour quelqu'un.

=> Une story bien formulée n'est pas une story qui a de la valeur.

## Ce que l'IA change : le prix d'une question

Le cours défend une idée simple, dans [Encaisser l'incertitude]({{< relref "philosophie/pourquoi_agile/encaisser_incertitude/index" >}}) :

> On ne réduit pas une incertitude en écrivant un document plus long, on la réduit en produisant quelque chose et en l'observant.

Chaque prototype, chaque incrément est donc une **question posée à l'utilisateur** : est-ce que cela vous sert ? Jusqu'ici, poser une question coûtait des jours ou des semaines de développement. Avec l'IA, elle peut coûter une heure.

Jainish Shah (Thoughtworks) présente le choix qui en découle :

> If AI helps us build a feature in two days instead of two weeks, we face a strategic choice: We can use the extra capacity to build more. Or we can use it to learn more. [^2]

Apprendre plus, précise-t-il, c'est tester des hypothèses sur les utilisateurs : tester plus d'idées, montrer le travail aux clients plus tôt, abandonner plus tôt celles qui ne tiennent pas [^2]. Il donne un exemple qui aurait été difficile il y a quelques années :

> A product manager can explore an idea with a customer and create a working prototype during the actual conversation using AI design tools. [^2]

C'est l'esprit du *pretotyping*, cité dans [MVP et pretotype]({{< relref "regard_critique/mvp_et_pretotype" >}}) : s'assurer de construire « The Right It before you build It right », la bonne chose avant de bien la construire.

> [!affirmation] Affirmation
> L'IA ne trouve pas la valeur. Elle rend moins cher le fait de la chercher.

### Ce qui ne s'accélère pas

Produire un prototype prend une heure. Faire en sorte qu'un utilisateur s'en serve, puis observer ce qu'il en fait, prend autant de temps qu'avant. La page [Sprint Review]({{< relref "frameworks/framework_scrum/ceremonies/review" >}}) le rappelait : « le mieux est de récupérer le feedback en regardant comment les utilisateurs prennent en main le produit ».

Yuval Yeret fait le même constat. L'IA aide beaucoup à coder, parce que le code se vérifie : on peut essayer plusieurs fois et voir si cela fonctionne. Elle aide beaucoup moins à savoir si ce qui est livré est utile :

> Validating value and outcomes is much harder. [^3]

=> L'IA raccourcit la moitié de la boucle de feedback : la production. L'autre moitié, l'observation de l'usage, reste à la vitesse des humains.

## Le risque : construire la mauvaise chose plus vite

Le temps gagné peut servir à apprendre plus, ou à construire plus. Dans le second cas, l'IA accélère le scénario que le cours décrit comme le plus coûteux, dans [Engager le client]({{< relref "philosophie/pourquoi_agile/engager_client" >}}) : « un logiciel irréprochable dont personne ne veut ».

Kaczor le dit sans détour :

> In fact, the risk of building the wrong things faster has never been higher. [^1]

Le cours a déjà l'argument contre cette dérive :

> Une fonctionnalité livrée dont personne ne se sert n'a pas une valeur nulle : elle a une valeur négative. Il faudra la maintenir, la tester et la porter à chaque migration.

L'IA baisse le coût de **fabrication** d'une fonctionnalité. Elle ne baisse pas le coût de sa **présence** dans le produit : il faut toujours la maintenir, la tester, la faire évoluer. C'est pourquoi le conseil de Jeff Patton, cité dans [Output vs Outcome]({{< relref "philosophie/pourquoi_agile/produire_valeur/output_vs_outcome" >}}), garde tout son sens : « your job is not to build more—it's to build less ».

=> Quand construire ne coûte presque rien, *build less* demande plus de discipline, pas moins.

Le rapport DORA 2025 mesure cet effet : sans attention portée à l'utilisateur, l'IA dégrade la performance des équipes au lieu de l'améliorer [^4]. Voir [IA et métriques DORA]({{< relref "ouvertures/agile_et_ia/ia_et_dora" >}}).

Le danger est aussi dans la façon de mesurer le succès. La page [Projet VS Produit]({{< relref "philosophie/pourquoi_agile/produire_valeur/projet_vs_produit" >}}) distingue deux logiques : « Le mode projet mesure ce qui a été livré à une date. Le mode produit mesure ce que le produit produit dans la durée. » Avec l'IA, livrer devient facile, donc le mode projet affiche des succès sans effort. Seul le mode produit permet de voir que ces livraisons ne servent à rien. Yeret le formule ainsi :

> In a forward-deployed world, the unit of value isn't a feature; it's a realized outcome. [^5]

## Le Product Owner devient la contrainte

Le cours définit le [Product Owner]({{< relref "frameworks/framework_scrum/responsabilites/product_owner" >}}) comme celui qui doit « Maximiser la valeur apportée au produit » et « Créer, prioriser et mettre à jour le Product Backlog ».

Quand l'équipe produit plus vite, le backlog se vide plus vite. Yeret décrit des équipes qui finissent par manquer de travail :

> Or it may create an environment where engineering is starved, because it does not have enough well-shaped work to pull. [^3]

Le travail ne manque pas en quantité : il manque du travail **bien défini**, dont on sait pour qui il est fait et pourquoi. Le goulot passe alors du développement à la décision (voir [L'IA déplace le goulot]({{< relref "ouvertures/agile_et_ia/goulot_deplace" >}})). Pour Kaczor, la compétence clé du PO change :

> when AI increases development velocity, the Product Owner's ability to say "no" becomes their most valuable skill. [^1]

Le cours signalait déjà un obstacle fréquent, dans [Engager le client]({{< relref "philosophie/pourquoi_agile/engager_client" >}}) : un Product Owner qui « n'a ni le mandat de décider, ni l'accès aux utilisateurs finaux ». Avant l'IA, ce défaut ralentissait l'équipe sans qu'on le remarque toujours. Avec l'IA, il se voit tout de suite : l'équipe attend des décisions, ou pire, construit sans elles.

> [!affirmation] Affirmation
> L'IA ne trouve pas la valeur métier. Elle baisse le prix des questions qu'on peut poser à l'utilisateur, et rend plus coûteux le fait de ne pas les poser.

[^1]: Krystian Kaczor, [Do We Need to Rewrite Scrum in the Age of AI?](https://www.scrum.org/resources/blog/do-we-need-rewrite-scrum-age-ai), scrum.org (2025)
[^2]: Jainish Shah, [AI makes Agile more alive](https://www.thoughtworks.com/insights/blog/agile-engineering-practices/ai-makes-agile-more-alive), Thoughtworks (2026)
[^3]: Yuval Yeret, [AI Made Engineering Faster. Why Didn't Value Follow?](https://yuvalyeret.com/blog/ai-coding-moved-the-bottleneck/) (2026)
[^4]: DORA, [State of AI-assisted Software Development 2025](https://services.google.com/fh/files/misc/2025_state_of_ai_assisted_software_development.pdf), p. 60
[^5]: Yuval Yeret, [AI Didn't Kill Agile. It Moved the Bottleneck.](https://yuvalyeret.com/blog/ai-didnt-kill-agile-it-moved-the-bottleneck/) (2026)
