# France Care, accès aux soins et prévention en France

Le plugin France Care aide Claude à répondre à trois questions : **où se soigner autour
d'une commune française** ; **que valent les indicateurs d'accès aux soins** d'un
territoire ; **quelle action de prévention santé mener en entreprise**, et à quel moment de
l'année. Il s'appuie sur des données publiques (répertoire FINESS des établissements,
accessibilité potentielle localisée de la DREES, INSEE) que France Care corrige,
géolocalise et met à jour chaque jour, et sur le guide sourcé des animations santé en
entreprise de France Care.

## Installer

**Claude Code** (2.1.275 ou plus récent) :

```
/plugin install france-care --marketplace France-Care/claude-plugin-france-care
```

Versions antérieures : `/plugin marketplace add France-Care/claude-plugin-france-care`, puis
`/plugin install france-care@france-care`.

**Claude (web, bureau, mobile)** : ajoutez un connecteur personnalisé avec l'adresse
`https://mcp.france-care.fr/mcp`. Aucun compte n'est demandé. Le connecteur donne les
outils ; les trois skills ne viennent qu'avec le plugin.

## Ce que contient le plugin

- **Le connecteur France Care** (`https://mcp.france-care.fr/mcp`), cinq outils en
  lecture et un signalement anonyme :
  - `analyze_territory` : accès aux soins d'une commune, de son intercommunalité, de son
    département et de sa région ;
  - `compare_territories` : deux territoires sur les mêmes indicateurs ;
  - `search_health_infrastructure` : établissements de santé autour d'un lieu, triés par
    distance, avec leur téléphone quand il est public ;
  - `signaler_besoin_non_couvert` : signaler, avec l'accord de la personne, qu'elle n'a
    pas trouvé de soignant dans sa commune ;
  - `animations_sante_entreprise` : les fiches validées du guide des animations santé en
    entreprise, par thème ou par mois (déroulé, coût, partenaires, sources, date de
    vérification, lien) ;
  - `calendrier_sante` : les journées, semaines et mois de santé de l'année.
- **Trois skills** :
  - `trouver-ou-se-soigner` : chercher les lieux de soins proches et les démarches utiles
    (médecin traitant, permanence des soins, pharmacie de garde) ;
  - `lire-indicateurs-acces-aux-soins` : lire l'APL sans contresens (unités, seuil de
    la DREES, moyenne nationale) et répondre à « désert médical ? » par les classements
    officiels (zonage de l'ARS, zones prioritaires du Pacte) ;
  - `preparer-une-animation-sante` : proposer à un employeur, un CSE ou un préventeur deux
    ou trois animations sourcées, sans chiffre inventé, et bâtir le calendrier de
    prévention de l'année.

Documentation : https://mcp.france-care.fr/plugin

## Exemples

- « Où trouver un dentiste près de Guéret ? »
- « Ma commune manque-t-elle de médecins ? J'habite à Fontainebleau. »
- « Compare l'accès aux soins entre Rodez et Millau. »
- « Qu'est-ce qu'on peut organiser pour Octobre rose dans une PME de bureaux ? »
- « Quelles journées de santé tombent en novembre ? »

## Données et confidentialité

Le connecteur ne demande aucun compte. Il reçoit le nom de commune, le code postal ou le
type d'établissement que Claude lui transmet ; pour la prévention, le thème ou le mois. Il ne conserve ni la question ni la
réponse. Aucune donnée de santé personnelle n'est demandée ni traitée.

Les journaux techniques du serveur web gardent l'adresse IP et l'adresse appelée, pas le
contenu de la requête, pendant 14 jours. Ils servent à la sécurité et à la limitation
des abus.

Ce qui est enregistré, sur les serveurs de France Care en France : des totaux quotidiens
anonymes des recherches (commune ou département, type de lieu, recherche vide ou non) et
des signalements de besoins non couverts (commune, profession, nature du manque, sur
listes fermées) ; pour la prévention, des totaux par jour, outil et thématique du guide
ou mois, jamais les mots saisis. Ni adresse IP, ni texte saisi, ni session. France Care s'en sert pour
mesurer où la demande de soins reste sans réponse.

Les signalements alimentent une carte publique, en données ouvertes :
https://alice.france-care.fr/besoins. Une commune n'y apparaît qu'à partir de 5
signalements.

Le plugin ne recueille aucune coordonnée. Une personne qui souhaite être accompagnée par
un conseiller France Care reçoit le lien de sa page de contact, où elle donne elle-même
son accord.

Le plugin n'envoie rien à un autre service que ce connecteur. Politique de
confidentialité : https://mcp.france-care.fr/confidentialite. Exercice de vos droits :
dpo@france-care.fr.

France Care oriente. Le plugin ne pose pas de diagnostic et ne remplace pas un professionnel de
santé. En cas d'urgence, appelez le 15 ou le 112.

## Sources

DREES (APL, millésime 2023), FINESS (synchronisé chaque jour), zonage des ARS (fichier
national DataSanté), ministère de la Santé (zones prioritaires du Pacte), INSEE, RNA ;
guide France Care des animations santé en entreprise
(https://www.france-care.fr/entreprise/animations-sante), dont chaque fiche cite ses
sources. Méthodologie
détaillée : ressource `france-care://methodology` du connecteur.

## Intégrer votre service

Vous éditez un service de santé (téléconsultation, réseau de soins, centre, application
de prévention) et vous souhaitez que ses données soient accessibles à Claude par France Care :
écrivez-nous à contact@france-care.fr.

## Support

contact@france-care.fr

## Éditeur

France Care (Care Connect SAS), https://www.france-care.fr. Licence MIT pour le contenu
de ce dépôt ; le serveur et ses données sont servis par France Care.
