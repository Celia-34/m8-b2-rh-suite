# Fiche de décision en 3-4 pages — Mini-cours

> Brief associé : M8-B2
> Durée de lecture : ~20 min
> Pré-requis : cadrages M8-B1 + décisions de groupe (§1)
> *(nom de fichier historique « 10pages » : le format actuel est une fiche de 3-4 pages)*

## Pourquoi cette techno ?

La fiche de décision est le **livrable technique** qui synthétise les
arbitrages et la conception pour un **architecte** (pas un décideur métier comme
le cadrage). Elle doit permettre à quelqu'un d'autre de **reprendre le projet**
en comprenant **pourquoi** chaque brique est là. En 2 h le mercredi matin, on
ne rédige pas un dossier : on **décide et on trace**. Elle réutilise l'acquis du
parcours (déploiement M5, monitoring M6, audit M7).

## Concepts clés

- **Public = architecte** : on peut être technique, mais structuré et justifié.
- **Un seul fichier, 7 sections + annexe** : décisions de groupe / 5 arbitrages /
  architecture finale (Mermaid) + ce qu'on n'a pas mis / évaluation /
  déploiement & monitoring / conformité & sécurité / coûts / annexe questions.
- **Tableaux d'abord** : les arbitrages, le monitoring, les coûts tiennent en
  tableaux ; le texte sert à expliquer les liens.
- **Traçabilité** : chaque brique du schéma découle d'un arbitrage ou d'une
  contrainte client (dont l'imprévu de mardi).
- **Sobriété visible** : « ce qu'on n'a PAS mis » (vector DB, Registry, agents)
  avec la justification.
- **Références aux modules** : « CI/CD comme en M5 », « dérive comme en M6 » —
  capitalisation explicite, en une ligne.
- **3-4 pages = un plafond** : le pseudo-code est un bonus ⭐, pas une section due.

## Exemple minimal qui tourne

```markdown
## 3. Architecture finale et sobriété
Mail → pseudonymisation → classifieur TF-IDF + régression logistique → routage
(confiance < 0.6 → revue humaine) → journal.
**Ce qu'on n'a PAS mis** : pas de vector DB (RAG = non), pas de MLflow Registry
(1 modèle, réentraînement trimestriel), pas d'agent (prédiction unique).
```

## Exercice guidé

À partir de vos arbitrages (§2) :
1. Dessinez le schéma Mermaid final (§3) : 4-6 briques, pas plus.
2. Pour chaque brique, retrouvez l'arbitrage ou la contrainte qui la justifie.
3. Écrivez « ce qu'on n'a PAS mis » (3 lignes minimum).
4. Remplissez le tableau de monitoring (§5) avec des seuils chiffrés.

*Solution attendue* : un schéma où aucune brique n'est orpheline, et une section
sobriété qui cite au moins 2 briques écartées.

## Pièges fréquents

| Piège | Conséquence |
|---|---|
| Rédiger en paragraphes longs | Dépassement des 4 pages, rien de lisible |
| Tout détailler (code complet) | C'est de la conception, pas un POC |
| Pas de référence aux modules | On réinvente, on ne capitalise pas |
| Sobriété invisible | Critère manqué |
| Archi incohérente avec les arbitrages | Perte de traçabilité |
| Oublier l'imprévu client | Conception qui ignore une contrainte connue |

| Symptôme | Cause probable |
|---|---|
| L'architecte ne peut pas reprendre | Fiche trop vague ou incohérente |
| Briques inexpliquées | Pas de lien arbitrage → archi |
| Fiche trop longue | Texte au lieu de tableaux |
| Question « et la DPO / la direction ? » sans réponse | Imprévu non intégré en §6 |

## Pour aller plus loin

- Cf. déploiement M5, monitoring M6, audit M7 — à référencer.
- MLOps principles : https://ml-ops.org/content/mlops-principles

## Vérification (checklist apprenant)

- [ ] 3-4 pages **au maximum**, 7 sections + annexe.
- [ ] Lisible par un architecte (technique mais clair).
- [ ] Références aux modules antérieurs (M5/M6/M7).
- [ ] Section « ce qu'on n'a PAS mis » (sobriété).
- [ ] Chaque brique d'archi découle d'un arbitrage ou d'une contrainte client.

> 💡 **Récap — Fiche de décision** : public = **architecte** ; **3-4 pages au maximum**, tableaux d'abord ; **référencer les modules** (CI/CD M5, monitoring M6) ; « ce qu'on n'a PAS mis » (sobriété) ; chaque brique découle d'un arbitrage (traçabilité). Assez claire pour qu'un autre reprenne.

### À retenir

- Le livrable se juge sur sa **clarté pour le destinataire**, pas sur sa longueur.
- **Chiffrer** plutôt qu'affirmer : un nombre vaut mieux qu'un adjectif.
- **Sobriété** : recommander le plus simple qui résout le besoin, et **dire ce qu'on écarte**.
- Tracer ses **choix** et leur **raison** — c'est ce qui se défend en restitution.
