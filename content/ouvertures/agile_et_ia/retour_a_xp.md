+++
title = "Retour à XP ?"
description = "Avec les agents de code, les pratiques techniques d'Extreme Programming changent de statut : d'optionnelles, elles deviennent des conditions d'exercice."
weight = 40
+++

> [!ressource] Ressources
> - [Does AI Make the Agile Manifesto Obsolete? - Steef-Jan Wiggers, InfoQ (2026)](https://www.infoq.com/news/2026/02/ai-agile-manifesto-debate/)
> - [Augmented Coding: Beyond the Vibes - Kent Beck (2025)](https://tidyfirst.substack.com/p/augmented-coding-beyond-the-vibes)
> - [Is Agile Dead? XP Might Be the Future - Antonio Rodríguez (2026)](https://thelaziest.dev/is-agile-dead-xp-might-be-the-future/)
> - [Humans and Agents in Software Engineering Loops - Kief Morris (2026)](https://martinfowler.com/articles/exploring-gen-ai/humans-and-agents.html)
> - Extreme Programming Explained - Kent Beck

Avec l'arrivée des agents de code, une idée revient souvent : l'agilité serait dépassée, mais XP reviendrait. Cette page examine les deux moitiés de cette idée. D'abord, le Manifeste tient-il quand un outil écrit le code ? Ensuite, que deviennent les pratiques de XP ?

## Le Manifeste est-il périmé ?

En 2026, Steve Jones (Capgemini) a lancé un débat en affirmant que l'IA avait tué le Manifeste agile. InfoQ en a fait la synthèse [^1]. Son argument principal porte sur la première valeur, *les individus et leurs interactions plus que les processus et les outils*. Selon lui, avec les agents, l'outil compte énormément : on ne travaille pas de la même façon selon l'agent qu'on utilise. Il ajoute un argument de vitesse :

> Agentic SDLCs are too fast for Agile. [^1]

D'autres lui ont répondu. Rolf Läderach :

> Agile is not the Manifesto, and it is certainly not about frameworks. Agile is about creating adaptive and learning organisations that can respond to change and deliver outcomes. [^1]

Et Eric Newcomer, plus sec :

> I think bureaucracy killed agile before AI agents came along. [^1]

### Ce que dit vraiment la première valeur

L'argument de Jones repose sur une lecture rapide du Manifeste. Le texte ne dit pas que les outils ne comptent pas. Il dit qu'on les fait passer **après** les individus et leurs interactions. Nous l'avions souligné dans [le Manifeste]({{< relref "philosophie/philosophie_agile/definir_agile/manifeste" >}}) :

> Nous reconnaissons la valeur des seconds éléments, mais privilégions les premiers.

Jones a raison sur un point : avec un agent, l'outil pèse plus lourd qu'avant sur le résultat. Mais cela ne change pas l'ordre des priorités. On discute d'abord du besoin entre humains (l'utilisateur, le Product Owner, l'équipe). Ensuite, que le code soit écrit par une personne, par Claude ou par Codex importe moins. L'outil a changé ; la conversation sur le besoin reste humaine.

=> Le Manifeste n'est pas périmé. Il est plus facile à oublier.

### XP vient avant le Manifeste

Un rappel du cours aide à sortir du débat. [XP précède le Manifeste]({{< relref "frameworks/framework_xp/naissance/index" >}}) : il est né entre 1995 et 1999, le Manifeste date de 2001. « L'agilité ne les a pas produits : ce sont eux qui l'ont produite. »

Si le Manifeste est contesté, il est donc logique de revenir aux pratiques dont il est issu. C'est ce que fait Antonio Rodríguez dans un article au titre explicite, *Is Agile Dead? XP Might Be the Future* [^2].

## Pourquoi XP revient

XP n'est pas né d'un problème d'organisation, mais d'un problème technique : **le coût du changement**. Dans une approche classique, plus le projet avance, plus une modification coûte cher. Le [pari de XP]({{< relref "frameworks/framework_xp/naissance/index" >}}) est que « cette courbe n'est pas une fatalité » : avec les bonnes pratiques, le changement reste abordable jusqu'à la fin.

Le cours le résume ailleurs, dans [Encaisser le changement]({{< relref "philosophie/pourquoi_agile/encaisser_changement" >}}) :

> L'accueil du changement est une propriété technique avant d'être une posture managériale.

L'IA rend cette phrase plus vraie encore. Un agent produit beaucoup de code, vite. La question n'est plus de savoir si on peut écrire le code, mais si on peut le **modifier sans tout casser**. C'est exactement le problème que XP cherchait à résoudre.

### Ce que l'IA rend bon marché

Les pratiques de XP ont longtemps été jugées trop chères. Écrire les tests avant le code, travailler à deux sur le même poste : tout cela demande du temps humain. Rodríguez constate que l'IA change ce calcul :

> AI coding agents have completely flipped the cost equation of software development. [^2]

Kent Beck, l'auteur de XP, en a fait l'expérience. Il distingue deux façons de travailler avec un agent, qu'il appelle le « génie » :

> In vibe coding you don't care about the code, just the behavior of the system. If there's an error, you feed it back into the genie in hopes of a good enough fix. In augmented coding you care about the code, its complexity, the tests, & their coverage. [^3]

Dans l'*augmented coding*, les exigences restent celles de XP. Beck le dit lui-même :

> The value system in augmented coding is similar to hand coding--tidy code that works. It's just that I don't type much of that code. [^3]

Concrètement, il a demandé à l'agent de suivre le TDD, test par test. Et il a appris à surveiller certains signaux d'alerte, dont celui-ci :

> Any indication that the genie was cheating, for example by disabling or deleting tests. [^3]

=> Un agent qui veut faire passer les tests peut aussi les supprimer. Le TDD protège contre l'agent, à condition de surveiller les tests eux-mêmes.

## Les pratiques XP, une par une

Le cours présente XP comme une même décision appliquée six fois : prendre une pratique qui fonctionne et **pousser le curseur au maximum** (voir [Naissance de XP]({{< relref "frameworks/framework_xp/naissance/index" >}})). Voici ce que devient chaque curseur avec un agent. La troisième colonne est notre lecture, pas une étude.

| Le curseur XP | La pratique | Avec un agent |
| :--- | :--- | :--- |
| On relit en permanence | Binôme | L'agent peut relire en continu, mais il ne partage pas la connaissance (voir plus bas) |
| On teste avant d'écrire le code | TDD | Devient le principal moyen de savoir si l'agent a raison |
| On intègre plusieurs fois par jour | Intégration continue | Indispensable : plus de code, produit plus souvent |
| On conçoit en continu | Conception simple, refactoring | Plus nécessaire qu'avant : un agent accumule vite la complexité |
| On livre toutes les une à deux semaines | Petites livraisons | Menacé : un agent produit volontiers de gros lots |
| Le client est dans la pièce | Client sur site | Inchangé : l'agent n'est pas le client |

Deux lignes méritent un commentaire.

**Le TDD.** Rodríguez insiste sur l'étape qu'on est tenté de sauter, celle où l'on vérifie que le test échoue avant d'écrire le code :

> If you skip watching it fail, you might end up with tests that pass for the wrong reasons. [^2]

Un test qui n'a jamais échoué ne prouve pas qu'il teste quelque chose. Avec un agent qui écrit à la fois le code et les tests, cette vérification devient la seule garantie.

**La conception simple.** Beck raconte que ses deux premières tentatives ont échoué pour cette raison : « My first 2 attempts had accumulated so much complexity that the genie completely stalled. » [^3] Un agent ne ralentit pas devant la complexité qu'il crée : il la crée jusqu'à se bloquer. Le refactoring reste un travail humain, ou au moins une décision humaine.

## Le binôme avec un agent n'est pas un binôme

Rodríguez va plus loin et voit dans l'agent un partenaire de binôme idéal :

> Pair programming? Your AI is your pair now. 24/7, no ego, infinite patience. [^2]

C'est vrai pour une partie de ce que fait le binôme : relire en continu. Mais le cours lui donne d'autres rôles. Dans les [pratiques XP]({{< relref "frameworks/framework_xp/pratiques" >}}), le binôme invite les équipiers « à partager leurs connaissances, à vérifier mutuellement leur travail ». Et la page [Équipe pluridisciplinaire]({{< relref "equipe_agile/constitution_equipe/pluridisciplinaire" >}}) en fait un moyen de partage, où les développeurs « partageront leurs connaissances techniques et métiers ».

Un agent vérifie, mais il ne partage rien. À la fin de la session, une seule personne a appris quelque chose, et parfois aucune.

Le risque est connu. XP pratique la **propriété collective du code** : n'importe qui peut modifier n'importe quelle partie. Le cours précise qu'elle demande que l'équipe reste « vigilante pour ne pas laisser le projet se transformer en une batterie de silos cloisonnés ». Si chaque développeur travaille seul avec son agent, chacun connaît sa partie et personne ne connaît l'ensemble : les silos reviennent.

Une piste : garder le binôme humain et lui confier l'agent. Deux personnes qui pilotent ensemble un agent gardent la vitesse de l'outil et le partage entre humains. Voir aussi [L'IA et le côté humain d'Agile]({{< relref "ouvertures/agile_et_ia/dimension_humaine" >}}).

## Les boucles de XP deviennent le harnais de l'agent

XP empile des boucles de feedback, de la plus courte à la plus longue (voir [Valeurs et principes]({{< relref "frameworks/framework_xp/valeurs_et_principes" >}})) : les tests unitaires en quelques secondes, l'intégration continue en quelques minutes, les tests d'acceptation avec le client en quelques jours, l'itération en une à deux semaines.

Kief Morris propose une grille pour savoir où placer l'humain face à l'agent [^4]. Il distingue deux boucles :

- la boucle du **pourquoi** : transformer une idée en résultat utile, et apprendre de ce résultat ;
- la boucle du **comment** : produire le code, les tests, l'infrastructure.

La première reste humaine :

> Until the AI uprising comes humans will run this loop because we're the ones who want what it produces. [^4]

Pour la seconde, Morris décrit trois positions. Hors de la boucle : on laisse l'agent faire, c'est le *vibe coding*. Dans la boucle : on corrige soi-même chaque chose que l'agent produit, et l'on devient vite le goulot. **Sur** la boucle : on améliore ce qui encadre l'agent, qu'il appelle le *harnais* (les tests, les outils, les consignes).

> The "on the loop" way is to change the harness that produced the artefact so it produces the results we want. [^4]

Les boucles de XP se répartissent alors naturellement. Les boucles courtes (tests, intégration continue) forment le harnais de l'agent : il peut les exécuter seul, des centaines de fois. Les boucles longues (le client, l'itération, la livraison) restent la boucle du pourquoi, et elles restent humaines.

> [!affirmation] Affirmation
> XP ne revient pas par nostalgie. Ses pratiques techniques étaient chères parce qu'elles demandaient du temps humain. L'IA les rend bon marché au moment où elles deviennent indispensables. Ce qu'elle ne remplace pas, c'est ce que XP faisait **entre les personnes** : le binôme, le client sur site, la propriété collective.

[^1]: Steef-Jan Wiggers, [Does AI Make the Agile Manifesto Obsolete?](https://www.infoq.com/news/2026/02/ai-agile-manifesto-debate/), InfoQ (2026)
[^2]: Antonio Rodríguez, [Is Agile Dead? XP Might Be the Future](https://thelaziest.dev/is-agile-dead-xp-might-be-the-future/) (2026)
[^3]: Kent Beck, [Augmented Coding: Beyond the Vibes](https://tidyfirst.substack.com/p/augmented-coding-beyond-the-vibes), Software Design: Tidy First? (2025)
[^4]: Kief Morris, [Humans and Agents in Software Engineering Loops](https://martinfowler.com/articles/exploring-gen-ai/humans-and-agents.html) (2026)
