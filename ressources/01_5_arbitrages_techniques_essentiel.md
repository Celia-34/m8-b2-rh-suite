# Les 5 arbitrages techniques — Mini-cours

> Brief associé : M8-B2
> Durée de lecture : ~25 min
> Pré-requis : cadrage M8-B1, grille C4 (M4), 3 archis M7-B2

## Pourquoi cette techno ?

Concevoir, c'est **trancher**. Pour chaque projet IA, 5 questions reviennent :
ML ou DL ? SLM ou LLM ? RAG ou pas ? Agents ou pas ? Zero-shot suffit-il ? Les
expliciter et les **justifier** (au lieu de choisir « ce qui est à la mode ») est le
cœur du palier final C4/C7. La grille de notation **pondère la sobriété** :
recommander le plus **léger** qui résout le besoin.

## Concepts clés

- **Chaque arbitrage = choix + 2-3 raisons (≥ 1 chiffrée) + condition de
  changement d'avis**, en **une ligne du tableau §2** de la fiche de décision. La condition montre qu'on a réfléchi aux limites, pas dogmatisé.
- **« Non applicable » est une réponse valide** : les 5 questions sont une
  **grille de vérification**, pas une obligation d'introduire de la GenAI. Pour
  une reco sur historique d'achats ou une maintenance sur capteurs, « SLM vs
  LLM », « RAG » ou « zero-shot » peuvent se noter *non applicable : aucun modèle
  génératif requis* — en **1 ligne justifiée** + la condition qui ferait se poser
  la question. Forcer un choix là où il n'y a pas de question, c'est réintroduire
  le tropisme par la grille.
- **ML vs DL** : assez de données pour du DL ? Complexité minimale suffisante ?
- **SLM vs LLM** : la tâche justifie-t-elle un gros modèle, ou un petit (1-3B) suffit ?
- **RAG** : y a-t-il un **corpus à interroger** ? Sa qualité justifie-t-elle la
  complexité (embeddings + vector store) ? **Coût sécurité** : tout document
  indexé peut véhiculer une **injection indirecte** → filtrage du corpus à
  prévoir (cf. mini-cours 07 de M8-B1).
- **Agents** : **chaîne de raisonnement** multi-étapes, ou **prédiction unique** ?
  **Coût sécurité** : périmètre de droits + actions non supervisées → **moindre
  privilège** toujours ; **validation humaine requise selon l'impact** de
  l'action, les **droits** de l'agent et son **irréversibilité** (lire un
  document ≠ envoyer un courrier ou modifier un dossier). Un agent superviseur
  ne crée pas à lui seul une supervision effective : il faut qui valide, avec
  quelle autorité, dans quel délai, avec quelle trace (cf. mini-cours 07 de M8-B1).
- **Zero-shot** : a-t-on un **dataset labellisé** (→ supervisé meilleur) ou un
  démarrage à froid (→ zero-shot baseline) ?
- **Anti-tropisme** : le réflexe est « non » par défaut à LLM/RAG/agents, sauf gain
  prouvé. La cohérence compte (RAG non ⇒ pas de vector DB dans l'archi).

## Exemple minimal qui tourne

```markdown
# Arbitrage 4 — Agents : non
Statut : tranché. Choix : NON.
1. Prédiction atomique, pas de chaîne de raisonnement.
2. Sur-engineering (orchestration, coût, opacité).
3. Explicabilité > agents pour la DRH.
Condition de changement : si le workflow devenait multi-étapes hétérogène.

# Arbitrage 2 — SLM vs LLM : non applicable
Statut : non applicable — aucun modèle génératif : la sortie est un score
calculé sur des données tabulaires.
Condition qui ferait se poser la question : produire du texte pour l'utilisateur.
```

## Exercice guidé

Pour votre cas (en groupe) :
1. Remplissez le tableau §2 de la fiche (choix + 2-3 raisons + condition, ou « non applicable » justifié).
2. Vérifiez la **cohérence** : votre archi reflète-t-elle vos choix ?
3. Identifiez où la **sobriété** vous fait dire « non » — et assumez-le.

## Pièges fréquents

| Piège | Conséquence |
|---|---|
| « On hésite » | Arbitrage non tranché = critère manqué |
| Répondre « SLM » sur un cas sans texte à produire | GenAI forcée par la grille — c'était « non applicable » |
| Choisir LLM/agents par mode | Tropisme pénalisé |
| Pas de condition de changement d'avis | Choix dogmatique |
| Archi incohérente avec les arbitrages | Vector DB alors que RAG = non |
| Raisons non chiffrées | Arbitrage faible |

| Symptôme | Cause probable |
|---|---|
| Jury : « pourquoi pas plus simple ? » | sobriété non argumentée |
| Archi contient des briques inutiles | arbitrages non reflétés |
| Choix contestable | pas de raisons solides (aucune chiffrée) |

## Pour aller plus loin

- Grille de décision C4 (M4-B1) — structure de choix.
- 3 schémas M7-B2 (ML / RAG / agents) — patrons.

## Vérification (checklist apprenant)

- [ ] Les 5 arbitrages sont **tranchés** ou **non applicables** (justifié en 1 ligne).
- [ ] Chaque arbitrage tranché : choix + 2-3 raisons (≥ 1 chiffrée) + condition, une ligne du tableau §2.
- [ ] L'archi est **cohérente** avec les arbitrages.
- [ ] La sobriété est visible (« non » assumés et justifiés).
- [ ] Les raisons sont chiffrées quand c'est possible.

> 💡 **Récap — 5 arbitrages** : ML/DL · SLM/LLM · RAG · agents · zero-shot — chacun : choix + 2-3 raisons + **condition de changement d'avis** — ou **non applicable** justifié. Réflexe : « non » par défaut à LLM/RAG/agents sauf gain prouvé ; cohérence archi (RAG non ⇒ pas de vector DB) ; sobriété notée.

### À retenir

- Le livrable se juge sur sa **clarté pour le destinataire**, pas sur sa longueur.
- **Chiffrer** plutôt qu'affirmer : un nombre vaut mieux qu'un adjectif.
- **Sobriété** : recommander le plus simple qui résout le besoin, et **dire ce qu'on écarte**.
- Distinguer ce qu'on **sait** de ce qui reste **à clarifier** (questions ouvertes).
- Tracer ses **choix** et leur **raison** — c'est ce qui se défend en restitution.
