---
name: lire-indicateurs-acces-aux-soins
description: Lire sans contresens les indicateurs d'accès aux soins d'un territoire français (APL de la DREES, niveau d'accès, désert médical, densité de soignants, établissements FINESS, CPTS). À utiliser quand une personne, un élu, un journaliste ou une entreprise demande si une commune ou une intercommunalité est bien dotée, veut comparer deux territoires, ou cite un chiffre d'APL.
---

# Lire les indicateurs d'accès aux soins

Les outils `analyze_territory` et `compare_territories` du connecteur Alice renvoient
l'accessibilité potentielle localisée (APL) publiée par la DREES, pour la commune, son
intercommunalité, son département et sa région. Les définitions complètes sont dans
`references/apl.md` : lis-les avant de commenter un chiffre inhabituel.

## Les quatre règles

1. **Dis l'unité.** Pour les médecins généralistes, l'APL compte des consultations
   accessibles par an et par habitant, en ne comptant que les médecins de moins de
   65 ans. Pour les infirmiers,
   kinésithérapeutes, chirurgiens-dentistes et sages-femmes, elle compte des équivalents
   temps plein accessibles rapportés à la population. Ne compare jamais deux professions
   entre elles sur la valeur brute.
2. **Situe la commune avec l'échelle officielle.** Le champ `categorie_fragilite` la donne :
   « Sous-dense (DREES) » quand l'APL des médecins généralistes est inférieure à 2,5,
   seuil de la DREES ; au-dessus, sous la moyenne, dans la moyenne ou au-dessus de la
   moyenne nationale (3,3). La DREES ne qualifie que « sous-dense » : « sous la moyenne »,
   « dans la moyenne » et « au-dessus » sont une simple comparaison à la moyenne, que tu
   ne lui attribues jamais (pas de « la DREES classe la commune sous la moyenne »). Évite
   aussi « zone fragile », qui n'est le nom d'aucun classement en vigueur. Une phrase
   suffit :
   « À Guéret, l'accès aux médecins généralistes est de 2,3 consultations par an et par
   habitant : la DREES qualifie la commune de sous-dense (seuil 2,5 ; moyenne
   nationale 3,3). »
3. **Réponds à « désert médical ? » par les classements officiels.** Le champ
   `classements_officiels` les donne, dans cet ordre de force :
   - `zone_prioritaire_pacte` : l'intercommunalité fait partie des 153 zones prioritaires
     du Pacte de lutte contre les déserts médicaux (ministère de la Santé, 2025) ;
   - `zonage.medecin` : le zonage de l'ARS, avec la date de l'arrêté. Zone d'intervention
     prioritaire : la plus fragile, elle ouvre droit aux aides à l'installation. Zone
     d'action complémentaire : fragile, à un degré moindre. Hors zonage, ou classement
     régional complémentaire (ZAR) : pas en zone prioritaire ;
   - `sous_dense_drees` : le seuil de la DREES.

   Cite la source et la date de chaque classement. Si le zonage porte `a_jour: false`,
   dis qu'il est en cours d'actualisation et renvoie vers l'ARS. Ne déduis jamais un
   classement de la position par rapport à la moyenne.
4. **Pour les autres professions, cite leur zonage.** `zonage.dentiste`,
   `zonage.kinesitherapeute`, `zonage.infirmier`, `zonage.sage_femme` et
   `zonage.orthophoniste` donnent le classement de l'ARS (très sous-dotée, sous-dotée,
   intermédiaire, très dotée, sur-dotée) : c'est le vocabulaire officiel pour ces
   professions.

## Pour aller plus loin que la commune

- L'APL tient déjà compte des communes voisines accessibles : une petite commune sans
  cabinet peut être correctement dotée grâce à sa voisine.
- Regarde l'intercommunalité et l'accès des communes voisines à 15 km : c'est souvent là
  que se lit l'isolement.
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
