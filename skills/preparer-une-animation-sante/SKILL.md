---
name: preparer-une-animation-sante
description: Préparer une action de prévention santé en entreprise à partir du guide sourcé de France Care. À utiliser quand un employeur, un DRH, un responsable RSE ou QVCT, un élu de CSE, un préventeur ou un service de santé au travail cherche une idée d'animation, d'atelier, de stand ou de campagne pour ses salariés, sur un thème (troubles musculosquelettiques, santé mentale, risques psychosociaux, dépistage des cancers, tabac, alcool, sommeil, écrans, salariés aidants, vaccination…) ou pour une date (Octobre rose, Movember, Mois sans tabac, Mars bleu, journée mondiale), ou veut bâtir le calendrier de prévention de l'année.
---

# Préparer une animation de prévention santé en entreprise

Le connecteur France Care donne deux outils :

- `animations_sante_entreprise` : les fiches validées du guide France Care des animations
  santé en entreprise. Chaque fiche dit le problème réglé, le déroulé, le coût, la
  préparation, les partenaires, l'efficacité publiée, ses sources et sa date de
  vérification, avec le lien vers la fiche.
- `calendrier_sante` : les journées, semaines et mois de santé de l'année.

## 1. Comprendre la demande

Repère le thème, le moment (un mois, une campagne) et ce que l'entreprise peut engager :
budget, temps de préparation, présence d'un service de santé au travail ou d'un CSE, type
de site (bureaux, atelier, entrepôt, travail posté). Ne pose pas plus d'une question : si
le thème ou le mois est donné, cherche d'abord.

## 2. Chercher

- Un thème : `animations_sante_entreprise` avec `sujet` (les mots de la personne
  suffisent : « TMS », « burn-out », « dépistage du cancer du sein »).
- Une campagne nommée (Octobre rose, Movember, Mois sans tabac, Mars bleu, Dry January) :
  passe son nom en `sujet`, l'outil la ramène à son mois et à sa thématique.
- Un mois sans thème : `mois` seul.
- Une demande vague (« des idées de prévention ») : appelle l'outil sans argument, il rend
  les thématiques ; propose-en trois qui collent à l'entreprise.
- Un plan de l'année ou « quand faire quoi » : `calendrier_sante`, puis les fiches des
  thématiques liées (`animations_liees`).

Si la recherche ne rend rien, relance avec une thématique de la liste renvoyée, ou sans
`mois` : les fiches « toute l'année » ne sont rattachées à aucun mois.

## 3. Répondre

Propose deux ou trois fiches, pas toute la liste. Pour chacune, en quelques lignes :

1. le titre et ce qu'elle règle, en une phrase ;
2. si elle sensibilise ou se conclut par un geste du salarié (`effet`) ;
3. le déroulé, résumé en deux ou trois étapes ;
4. le coût et la préparation, tels que l'outil les donne ;
5. le partenaire public ou associatif à contacter (`partenaires`, `en_pratique`) ;
6. la source principale et le lien vers la fiche.

Classe-les selon ce que l'entreprise a dit pouvoir engager. Termine par le lien de la
page (`page`) pour voir le reste.

Pour un calendrier, donne les événements dans l'ordre, avec leur date telle qu'elle se
lit. Une date marquée `date_a_confirmer` est attendue, pas annoncée : dis-le. Si l'outil
renvoie une `note` sur l'année, répète-la.

## Ce que tu ne fais pas

- Tu n'inventes aucun chiffre : ni efficacité, ni taux de participation, ni coût. Quand
  `efficacite_publiee` vaut « non documenté », dis qu'aucune évaluation n'est publiée ;
  ne dis pas que l'animation « marche ».
- Tu n'inventes ni partenaire, ni contact, ni date : tout vient des outils, sinon tu le dis.
- Tu rappelles, quand l'animation touche au dépistage, à la vaccination ou à la santé
  mentale, que l'employeur ne reçoit aucune donnée de santé : ni qui participe, ni les
  résultats. La fiche le dit dans `vigilance` quand c'est un risque.
- Tu ne donnes pas d'avis médical aux salariés à travers l'animation : les gestes de
  santé se font avec les professionnels cités (service de santé au travail, médecin,
  pharmacien, Assurance maladie).
- Tu ne présentes pas les offres commerciales de France Care. Si l'entreprise demande
  qu'on l'accompagne pour organiser l'action, donne la page
  https://www.france-care.fr/entreprise/animations-sante.
