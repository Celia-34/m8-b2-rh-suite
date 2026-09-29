# Anticiper les questions (oral de 20 min) — Mini-cours

> Brief associé : M8-B2
> Durée de lecture : ~15 min
> Pré-requis : fiche de décision + schéma final — les questions vont en **annexe de la fiche**

## Pourquoi cette techno ?

Mercredi 11h15, chaque groupe a **20 minutes** : 12 min d'oral sur le schéma
final, puis **8 min de questions** du client et de la promo. Ce format reprend
la structure de la **soutenance certif** (présentation + questions), en plus
court. Les questions font souvent la différence : un groupe qui les a
**anticipées** paraît maître de son sujet ; un groupe pris au dépourvu doute.
Préparer **5 questions réalistes** suffit.

## Concepts clés

- **Questions réalistes** : pas « qu'est-ce qu'un LLM ? » mais « pourquoi pas un
  fine-tuning au lieu du zero-shot ? ». On creuse vos **choix**.
- **Les questions visent vos arbitrages** : chaque « non » (pas de LLM, pas de RAG)
  appelle un « pourquoi ? » → préparez la réponse.
- **Le client pose aussi des questions métier** : « et si ça se trompe ? »,
  « combien ça coûte ? », « et ma contrainte de mardi ? ».
- **Réponse = la condition de changement d'avis** : « on changerait si… » montre que
  le choix est réfléchi, pas dogmatique.
- **Anticiper la sobriété** : « c'est pas un peu simple ? » est la question reine.
- **Répartir** : chaque membre répond à au moins une question ; décidez-le avant.
- **Oral de 12 min** : 1 min besoin, 3 min décisions et arbitrages, 5 min schéma
  commenté, 2 min conformité / coûts, 1 min conclusion. Pas de slides.

## Exemple minimal qui tourne

```markdown
| # | Question | Réponse préparée | Qui |
|---|---|---|---|
| 1 | Pourquoi pas un LLM ? | 6 classes, 10 000 tickets labellisés : un classifieur classique suffit, ~10× moins cher, explicable. On changerait si les demandes devenaient des questions ouvertes à rédiger. | A |
| 2 | Et si le modèle se trompe ? | Erreur récupérable + seuil de revue humaine + suivi hebdo de la précision. | B |
```

## Exercice guidé

À partir de vos arbitrages :
1. Pour chaque « non » (LLM, RAG, agents), anticipez le « pourquoi ? ».
2. Ajoutez une question métier du client (coût, erreur, imprévu de mardi).
3. Gardez les 5 meilleures, réponses en 2-3 phrases chiffrées, et un nom par question.
4. Répétez l'oral une fois en chronométrant : 12 min, pas 15.

*Solution attendue* : 5 questions dont au moins 2 sur les arbitrages et 1 métier,
chacune attribuée à un membre.

## Pièges fréquents

| Piège | Conséquence |
|---|---|
| Questions triviales | N'entraîne pas le vrai échange |
| Préparer 20 questions | Dispersion, rien de solide |
| Réponses longues | On perd l'auditoire, les 8 min passent |
| Pas de chiffres | Réponses peu convaincantes |
| Ne pas répartir | Hésitation, un seul membre répond à tout |
| Oral non chronométré | Dépassement, plus de temps pour les questions |

| Symptôme | Cause probable |
|---|---|
| Pris au dépourvu | Questions non anticipées |
| Réponse dogmatique | Pas de condition de changement d'avis |
| Le client insiste sur sa contrainte | Imprévu de mardi non intégré |
| Un membre silencieux | Répartition non décidée |

## Pour aller plus loin

- Soutenance certif (présentation + questions sur le notebook) : ceci est l'entraînement.
- Cf. mini-cours `01_5_arbitrages_techniques` pour les conditions de changement d'avis.

## Vérification (checklist apprenant)

- [ ] 5 questions **réalistes** (pas triviales), dont au moins 1 métier.
- [ ] Chaque « non » d'arbitrage a sa réponse préparée.
- [ ] Réponses courtes (2-3 phrases), chiffrées si possible.
- [ ] La question « c'est pas trop simple ? » est anticipée.
- [ ] Chaque question a un membre qui répond ; l'oral tient en 12 min.

> 💡 **Récap — Questions prévues** : 5 questions **réalistes** ; chaque « non » d'arbitrage appelle un « pourquoi ? » → la réponse = la condition de changement d'avis ; anticiper « c'est pas trop simple ? » et la contrainte client ; réponses courtes, chiffrées, réparties entre les membres.

### À retenir

- **Chiffrer** plutôt qu'affirmer : un nombre vaut mieux qu'un adjectif.
- **Sobriété** : recommander le plus simple qui résout le besoin, et **dire ce qu'on écarte**.
- Tracer ses **choix** et leur **raison** — c'est ce qui se défend en restitution.
