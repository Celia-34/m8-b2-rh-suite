# Pseudo-code des composants critiques — Mini-cours

> Brief associé : M8-B2
> Durée de lecture : ~15 min
> Pré-requis : architecture conçue
> ⭐ **Optionnel** en M8-B2 : section bonus de la fiche de décision, à faire seulement si le reste est terminé.

## Pourquoi cette techno ?

En conception, on ne code pas — mais on doit montrer que les **composants
critiques** sont **réalisables**. Le pseudo-code (signatures + flow, sans syntaxe
précise) permet à un développeur qui prendrait la suite de comprendre **quoi
construire**, sans imposer une implémentation. C'est l'équilibre entre « trop
vague » (un schéma) et « trop précis » (du Python complet).

## Concepts clés

- **Niveau d'abstraction** : signatures (entrées/sorties) + flow (étapes), pas de
  détail de bibliothèque. « charge le modèle », pas `joblib.load(...)`.
- **Composants critiques uniquement** : 2-3 max, ceux qui portent le risque ou la
  valeur (le classifieur, la pseudonymisation, le seuil de décision).
- **Lisible par un dev** : un développeur doit pouvoir l'implémenter sans vous
  reposer la question.
- **Indépendant du langage** : le pseudo-code ne dit pas Python vs autre.
- **Montre les décisions clés** : seuils, fallback, gestion des cas limites.

## Exemple minimal qui tourne

```text
fonction classer_ticket(texte):
    texte_propre = pseudonymiser(texte)      # masque PII
    vecteur = vectoriser(texte_propre)
    proba, classe = predire(vecteur)
    si confiance(proba) < SEUIL:             # 0.6
        retourner ("revue_humaine", classe)
    retourner (classe)
```

## Exercice guidé

Pour votre conception :
1. Identifie les **2-3 composants critiques**.
2. Écris leur pseudo-code (signature + flow), sans syntaxe précise.
3. Vérifie qu'un dev pourrait l'implémenter sans te reposer de question.

## Pièges fréquents

| Piège | Conséquence |
|---|---|
| Pseudo-code = Python complet | On a codé alors qu'il fallait concevoir |
| Trop vague (juste un schéma) | Pas assez pour implémenter |
| Tous les composants | On noie le critique dans le trivial |
| Détails de bibliothèque | Impose une implémentation |
| Pas de cas limites | Le dev devra deviner |

| Symptôme | Cause probable |
|---|---|
| Le dev repose des questions | pseudo-code trop vague |
| Conception = prototype | trop précis, on a codé |
| Composant critique non couvert | mauvaise sélection |

## Pour aller plus loin

- Cf. composants critiques du correctif (classer_ticket).
- MLOps principles : https://ml-ops.org/content/mlops-principles

## Vérification (checklist apprenant)

- [ ] 2-3 composants critiques seulement.
- [ ] Signatures + flow, pas de syntaxe précise.
- [ ] Indépendant du langage / de la bibliothèque.
- [ ] Les décisions clés (seuils, fallback) apparaissent.
- [ ] Un dev pourrait l'implémenter sans question.

> 💡 **Récap — Pseudo-code** : signatures + flow, **pas** de syntaxe précise ; 2-3 composants **critiques** seulement ; indépendant du langage ; montrer les décisions clés (seuils, fallback). Équilibre entre « trop vague » (un schéma) et « trop précis » (du Python).

### À retenir

- Le livrable se juge sur sa **clarté pour le destinataire**, pas sur sa longueur.
- **Chiffrer** plutôt qu'affirmer : un nombre vaut mieux qu'un adjectif.
- **Sobriété** : recommander le plus simple qui résout le besoin, et **dire ce qu'on écarte**.
- Distinguer ce qu'on **sait** de ce qui reste **à clarifier** (questions ouvertes).
- Tracer ses **choix** et leur **raison** — c'est ce qui se défend en restitution.
