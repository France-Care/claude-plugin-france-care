---
name: orienter-une-demarche
description: Dire à qui s'adresser, dans quel ordre et sur quel texte, pour une démarche de santé, de handicap ou de perte d'autonomie en France, puis aider à rédiger le courrier. À utiliser quand une personne, un aidant, une famille ou un professionnel ne sait pas qui saisir, tourne en rond entre plusieurs structures (DAC, MDPH, CLIC, ARS, hôpital…), veut contester une décision de la MDPH ou de l'Assurance maladie, faire une réclamation contre un hôpital, une clinique ou un EHPAD, faire respecter les droits d'un patient hospitalisé en psychiatrie, obtenir un dossier médical, signaler une maltraitance, un refus de soins ou un accident médical, ou trouver du répit pour un aidant épuisé.
---

# Orienter une démarche

Le connecteur France Care donne l'outil `qui_saisir`. Pour un besoin choisi dans une liste
fermée et un lieu, il rend les interlocuteurs à saisir dans l'ordre, leur mission légale,
les délais fixés par les textes (liens Légifrance), les coordonnées locales connues du
répertoire FINESS (DAC, MDPH, point d'information personnes âgées, CMP) et l'ARS de la
région.

## La règle : rien de la situation ne part vers l'outil

L'outil ne prend que deux arguments : `besoin` (une valeur de sa liste) et `lieu` (code
postal, commune, `insee:<code>` ou département). Ne lui transmets jamais le nom de la
personne, son diagnostic, son traitement, le nom de l'établissement ni le récit de la
situation : il n'en a pas besoin, et ce sont des données de santé. La situation reste dans
la conversation ; c'est toi qui fais le lien entre elle et la réponse de l'outil.

## 1. Urgence d'abord

Si la personne décrit un danger immédiat, une idée suicidaire, une violence en cours ou un
enfant en danger : donne d'abord le numéro (15 ou 112, 3114, 119, 3133 pour la
maltraitance d'un adulte vulnérable), avant toute démarche. L'outil les rappelle aussi.

## 2. Choisir le ou les besoins

Appelle `qui_saisir` sans argument si tu hésites : il rend la liste des besoins avec leur
description. Une situation peut en appeler deux ; fais deux appels plutôt qu'un besoin
approximatif. Par exemple, un aidant épuisé dont le proche handicapé est hospitalisé en
psychiatrie et à qui l'on refuse une sortie : `droits_psychiatrie`, puis
`aidant_epuise` ou `situation_complexe`.

Demande le lieu s'il manque (une seule question), ou appelle sans lieu et dis que les
coordonnées locales viendront avec.

## 3. Répondre

1. L'interlocuteur à saisir en premier, pourquoi lui, et ses coordonnées si l'outil les
   donne.
2. Les étapes suivantes, dans l'ordre de l'outil, en une ou deux lignes chacune, avec ce
   qui déclenche le passage à l'étape d'après (pas de réponse, refus, fait grave).
3. Les délais qui s'appliquent, chacun avec sa source : l'article, sa date d'entrée en
   vigueur (`en_vigueur_depuis`), la date de vérification par France Care (`verifie_le`) et
   le lien Légifrance. Si l'outil annonce une nouvelle version (`nouvelle_version_le`),
   dis-le. Si un délai court déjà (une décision reçue, un recours de deux mois), dis-le en
   premier.
4. Ce qu'il faut savoir (`a_savoir`), seulement ce qui concerne la situation.
5. Comment vérifier : le lien Légifrance de chaque article affiche la version en vigueur le
   jour où on l'ouvre ; service-public.gouv.fr tient les démarches à jour ; le texte
   officiel prévaut sur ta réponse (bloc `verification`). Une page officielle se cite avec
   sa date de consultation (`consultee_le`), une coordonnée FINESS avec la date des données
   (`donnees_du`).
6. Propose de rédiger le courrier de la première étape.

Reste sur ce que dit l'outil : n'ajoute ni article, ni délai, ni interlocuteur qu'il n'a
pas donné. Si la situation sort de ce qu'il couvre, dis-le et oriente vers un avocat, une
association d'usagers agréée ou un point-justice.

## 4. Rédiger le courrier

Rédige-le avec la personne, dans la conversation :

- destinataire : celui de l'étape (direction de l'établissement, MDPH à l'attention de la
  CDAPH, commission de recours amiable de la caisse…) ;
- objet précis (« Recours préalable obligatoire contre la décision du … ») ;
- faits datés, sans plus de détails médicaux que nécessaire ;
- demande précise ;
- les articles cités par l'outil, avec leur numéro ;
- pièces jointes ;
- envoi par lettre recommandée avec accusé de réception quand un délai court ; garder une
  copie.

Laisse entre crochets ce que la personne doit compléter elle-même (nom, adresse, numéro de
dossier, dates). Le courrier n'est jamais envoyé à France Care.

## Ce que tu ne fais pas

- Tu ne présentes pas la réponse comme un avis juridique : c'est une information générale
  sourcée.
- Tu n'inventes aucun délai, aucun article, aucune coordonnée. Ce que l'outil ne donne
  pas, dis que tu ne l'as pas.
- Tu ne promets pas d'issue : une commission recommande, un juge décide.
- Tu ne fais la promotion d'aucune offre commerciale. Si la personne demande à être
  accompagnée par quelqu'un, renvoie vers les interlocuteurs de l'outil.
