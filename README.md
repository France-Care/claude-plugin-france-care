# Alice, accès aux soins en France

Alice aide Claude à répondre à deux questions : **où se soigner autour d'une commune
française** ; **que valent les indicateurs d'accès aux soins** d'un territoire. Elle
s'appuie sur des données publiques (répertoire FINESS des établissements, accessibilité
potentielle localisée de la DREES, INSEE) que France Care corrige, géolocalise et met à
jour chaque jour.

## Ce que contient le plugin

- **Le connecteur Alice** (`https://alice.france-care.fr/api/mcp`), en lecture seule :
  - `analyze_territory` : accès aux soins d'une commune, de son intercommunalité, de son
    département et de sa région ;
  - `compare_territories` : deux territoires sur les mêmes indicateurs ;
  - `search_health_infrastructure` : établissements de santé autour d'un lieu, triés par
    distance, avec leur téléphone quand il est public.
- **Deux skills** :
  - `trouver-ou-se-soigner` : chercher les lieux de soins proches et les démarches utiles
    (médecin traitant, permanence des soins, pharmacie de garde) ;
  - `lire-indicateurs-acces-aux-soins` : lire l'APL sans contresens (unités, moyenne
    nationale, différence avec le zonage des ARS).

## Exemples

- « Où trouver un dentiste près de Guéret ? »
- « Ma commune manque-t-elle de médecins ? J'habite à Fontainebleau. »
- « Compare l'accès aux soins entre Rodez et Millau. »

## Données et confidentialité

Le connecteur ne demande aucun compte. Il reçoit le nom de commune, le code postal ou le
type d'établissement que Claude lui transmet. Il ne conserve ni la question ni la
réponse. Aucune donnée de santé personnelle n'est demandée ni traitée.

Alice oriente. Elle ne pose pas de diagnostic et ne remplace pas un professionnel de
santé. En cas d'urgence, appelez le 15 ou le 112.

## Sources

DREES (APL, millésime 2023), FINESS (synchronisé chaque jour), INSEE, RNA. Méthodologie
détaillée : ressource `france-care://methodology` du connecteur.

## Intégrer votre service

Vous éditez un service de santé (téléconsultation, réseau de soins, centre, application
de prévention) et vous souhaitez que ses données soient accessibles à Claude par Alice :
écrivez-nous à contact@france-care.fr.

## Éditeur

France Care (Care Connect SAS), https://www.france-care.fr. Licence MIT pour le contenu
de ce dépôt ; le serveur Alice et ses données sont servis par France Care.
