# APL : définitions et références

## Source

Accessibilité potentielle localisée (APL), DREES, millésime 2023, calculée pour les 34 954
communes. Elle croise l'offre (praticiens et activité), la demande (population et
structure d'âge) et la distance (communes voisines accessibles en temps de trajet).

## Unités

| Profession | Unité | Référence nationale |
|---|---|---|
| Médecins généralistes | consultations accessibles par an et par habitant, médecins de moins de 65 ans seulement | 3,3 |
| Infirmiers | équivalents temps plein accessibles, rapportés à la population | 155,6 |
| Masseurs-kinésithérapeutes | équivalents temps plein accessibles, rapportés à la population | 120,0 |
| Chirurgiens-dentistes | équivalents temps plein accessibles, rapportés à la population | 61,0 |
| Sages-femmes | équivalents temps plein accessibles, rapportés à la population | 21,6 |

Les références nationales sont des moyennes pondérées par la population des communes.
Pour les médecins généralistes, c'est la variante « moins de 65 ans » que publie la DREES :
seuls les médecins de moins de 65 ans sont comptés dans l'offre, ce qui anticipe les
départs à la retraite.

## Seuil officiel

La DREES qualifie de **sous-dense** une commune dont l'APL aux médecins généralistes est
inférieure à 2,5 consultations par an et par habitant.

## Niveau d'accès (`categorie_fragilite`)

| APL médecins généralistes de la commune | Niveau |
|---|---|
| moins de 2,5 | Sous-dense (DREES) |
| 2,5 et moins de 95 % de la moyenne nationale | Sous la moyenne nationale |
| de 95 à 105 % de la moyenne | Dans la moyenne nationale |
| plus de 105 % de la moyenne | Au-dessus de la moyenne nationale |
| valeur absente | Non documenté |

## Classements officiels (`classements_officiels`)

| Champ | Classement | Source |
|---|---|---|
| `zone_prioritaire_pacte` | L'intercommunalité fait partie des 153 zones prioritaires | Pacte de lutte contre les déserts médicaux, ministère de la Santé (2025) |
| `zonage.medecin` | Zone d'intervention prioritaire, zone d'action complémentaire, hors zonage, classement régional complémentaire (ZAR, Bretagne et Occitanie) | ARS, article L.1434-4 du code de la santé publique, méthodologie de l'arrêté du 9 mai 2025 |
| `zonage.<profession>` | Très sous-dotée, sous-dotée, intermédiaire, très dotée, sur-dotée (orthophonistes : sous-dense) | ARS, zonage conventionnel de chaque profession |
| `sous_dense_drees` | APL médecins généralistes sous 2,5 | DREES |

Chaque zonage porte la date de l'arrêté régional. `a_jour: false` signale, pour les
médecins, une région dont l'arrêté en vigueur est plus récent que le fichier national
(consolidé DataSanté) : renvoyer vers l'ARS.

## Ce que l'APL n'est pas

- Un classement réglementaire : le zonage de l'ARS et les zones prioritaires du Pacte
  sont des classements distincts, donnés à part dans `classements_officiels`.
- Un délai de rendez-vous, une qualité de soins, ou l'assurance qu'un soignant accepte de
  nouveaux patients.
