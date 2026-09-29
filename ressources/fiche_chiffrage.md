# Fiche chiffrage — ordres de grandeur pour arbitrer

> Brief associé : M8-B2 · Lecture ~10 min · Complète la
> `cheatsheet_sobriete_couts.md` (repo `ia-atos-ressources`).
> **Usage** : vos arbitrages exigent des raisons **chiffrées**. Voici des
> ordres de grandeur défendables en 2026 — à ajuster à VOTRE volumétrie,
> et à recalculer, pas à recopier. Un chiffre sans calcul = déclaratif.

## 1. La formule qui sert partout

```
coût mensuel ≈ volume/mois × coût unitaire   (+ coût fixe d'infra)
```

Le **volume** vient de votre cadrage B1 (tickets/jour, recherches/jour,
scorings/heure…). C'est lui qui décide presque tout : 80 appels/jour et
80 000 appels/jour ne vivent pas dans le même monde.

## 2. Coûts unitaires — ordres de grandeur

| Option | Coût unitaire typique | Latence typique |
|---|---|---|
| Modèle ML classique local (LogReg, GBM) | ~0 € (CPU négligeable) | < 10 ms |
| Embedding (self-host, CPU) | ~0 € | 10-50 ms |
| SLM 7-8B self-host (GPU amorti) | fraction de centime / requête | 0,5-3 s |
| LLM API (classe milieu de gamme) | ~0,1-1 centime / requête courte | 1-5 s |
| LLM API (classe frontière, long contexte) | ~1-10 centimes / requête | 2-15 s |
| Chaîne d'agents (n appels LLM + outils) | n × le coût d'un appel, ×2-5 de marge | 5-60 s |

## 3. Coûts fixes — ordres de grandeur

| Poste | Ordre de grandeur |
|---|---|
| Serveur CPU (VPS/local) | 10-100 €/mois |
| Serveur GPU inference (cloud) | 300-1 500 €/mois selon carte |
| Poste/serveur GPU acheté (self-host) | 2-6 k€ une fois, amorti 3 ans |
| Jour·homme de développement (interne/ESN) | 400-900 € |
| Maintenance d'un composant de plus | comptez ~10-15 % du build/an |

## 4. Trois exemples de calcul (méthode, pas vérité)

- **80 appels/jour à un LLM API** : 80 × 22 j × ~0,5 ct ≈ **~10 €/mois** —
  le coût API n'est PAS l'argument ici ; l'argument est ailleurs
  (confidentialité, latence, dépendance).
- **50 000 affichages/mois avec appel LLM** : 50 000 × 0,5 ct ≈
  **250 €/mois** récurrents vs une table précalculée à ~0 € — là, le coût
  devient un argument.
- **Self-host GPU vs API** : 4 k€ amortis sur 3 ans ≈ 110 €/mois + exploitation.
  Rentable si le volume est élevé **ou** si la confidentialité l'impose
  (auquel cas ce n'est plus un calcul, c'est une contrainte).

## 5. Les pièges du chiffrage

| Piège | Conséquence |
|---|---|
| Chiffrer le run et oublier le build (jours·homme) | Option « pas chère » qui coûte 20 jours de dev |
| Oublier la maintenance (chaque brique de plus) | Dette opérationnelle invisible au dossier |
| Comparer des latences sans le volume | 2 s/requête est OK à 10/jour, rédhibitoire en page produit |
| Recopier cette fiche sans recalculer | Argument démonté en 1 question de jury |
| Coût énergie/API ignoré « car petit » | Sur 3 ans, le récurrent bat souvent le fixe |

## Vérification (checklist)

- [ ] Chaque arbitrage 2-5 a ≥ 1 raison chiffrée **calculée sur MA volumétrie**
- [ ] Le build (jours·homme) ET le run (€/mois) apparaissent au dossier
- [ ] La latence est confrontée au contexte d'usage (qui attend, combien de temps ?)
