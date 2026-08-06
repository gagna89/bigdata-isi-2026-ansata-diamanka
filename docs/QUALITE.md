\# Qualité des données — customers.csv (échelle 0.1)



| Défaut | Mesure | Colonne |

|---|---|---|

| Emails manquants (null+""+"N/A") | (ton chiffre, cellule 2.2) | email |

| Villes distinctes avant normalisation | 499 | ville |

| Villes distinctes après normalisation | 499 | ville |

| Doublons exacts | (ton chiffre, cellule 2.3) | (toutes) |

| Lignes brutes | 5025 | - |

| Lignes après nettoyage | 5000 | - |



\*\*Décisions prises :\*\*

\- Emails manquants : conservés avec drapeau `email\_valide=false` (pas de suppression de ligne).

\- Ville : accents retirés via `F.translate` (fonction native), pas d'UDF — meilleure performance.

\- Téléphone : normalisé sur 9 chiffres, préfixes valides 70/75/76/77/78.

\- Dédup : sur `email` après normalisation, sinon les quasi-doublons (casse email) survivent.



\*\*Tests :\*\* `pytest -q` → 4 tests, tous au vert (voir `pytest\_screenshot.png`).

