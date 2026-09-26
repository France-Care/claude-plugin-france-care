---
name: lire-indicateurs-acces-aux-soins
description: Lire sans contresens les indicateurs d'accès aux soins d'un territoire français (APL de la DREES, niveau d'accès, désert médical, densité de soignants, établissements FINESS, CPTS). À utiliser quand une personne, un élu, un journaliste ou une entreprise demande si une commune ou une intercommunalité est bien dotée, veut comparer deux territoires, ou cite un chiffre d'APL.
---

# Lire les indicateurs d'accès aux soins

Les outils `analyze_territory` et `compare_territories` du connecteur Alice renvoient
l'accessibilité potentielle localisée (APL) publiée par la DREES, pour la commune, son
intercommunalité, son département et sa région. Les définitions complètes sont dans
`references/apl.md` : lis-les avant de commenter un chiffre inhabituel.

## Les trois règles

1. **Dis l'unité.** Pour les médecins généralistes, l'APL compte des consultations
   accessibles par an et par habitant de moins de 65 ans. Pour les infirmiers,
   kinésithérapeutes, chirurgiens-dentistes et sages-femmes, elle compte des équivalents
   temps plein accessibles rapportés à la population. Ne compare jamais deux professions
   entre elles sur la valeur brute.
2. **Rapporte à la moyenne nationale.** La référence des médecins généralistes est 3,3.
   Le champ `categorie_fragilite` donne le niveau sur une échelle unique : très
   sous-doté (moins de 60 % de la moyenne), sous-doté (60 à 85 %), en tension (85 à
   100 %), correctement doté (au-delà). Cette échelle est celle de France Care appliquée
   aux chiffres de la DREES : n'écris jamais que la DREES « classe » une commune. Une
   phrase suffit : « À Guéret, l'accès aux
   médecins généralistes est de 2,3 consultations par an et par habitant, soit 30 % sous
   la moyenne nationale. »
3. **Ne confonds pas avec le zonage des ARS.** Ce niveau ne dit pas si la commune est
   classée zone d'intervention prioritaire. Ce classement relève de chaque agence
   régionale de santé et ouvre droit à des aides à l'installation. Si la personne parle de
   « désert médical », réponds sur l'accès mesuré. Précise que le classement officiel se
   vérifie auprès de l'ARS.

## Pour aller plus loin que la commune

- L'APL tient déjà compte des communes voisines accessibles : une petite commune sans
  cabinet peut être correctement dotée grâce à sa voisine.
- Regarde l'intercommunalité et la part de la population des communes très sous-dotées
  à 15 km : c'est souvent là que se lit l'isolement.
- Les établissements FINESS (maisons et centres de santé, hôpitaux, EHPAD, SSIAD) et
  l'existence d'une CPTS disent comment l'offre est organisée, pas combien de soignants
  exercent.

## Comparer deux territoires

`compare_territories` prend deux territoires par appel. Compare le même indicateur dans la
même unité ; commence par l'écart le plus parlant. Pour plus de deux territoires, enchaîne
plusieurs comparaisons.

## Limites à dire quand elles comptent

- Millésime 2023 : un départ ou une installation récents n'y figurent pas.
- L'APL mesure une accessibilité, pas la qualité des soins ni les délais de rendez-vous.
- Petites communes : quelques praticiens de plus ou de moins font varier fortement la
  valeur.
