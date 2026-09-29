# M8-B2 — Concevoir l'architecture cible (arbitrages explicites, groupe par client)

> **Repo template.** Groupe = les collègues staffés sur le **même client** en
> M8-B1 (binôme ou trio). **Un seul** membre fait « Use this template » →
> `M8-B2-conception-<cas>-<groupe>` et ajoute les autres en collaborateurs.
> **Pas de code** (pseudo-code ⭐ optionnel), **pas de slides**. Tout se fait en
> synchrone : **aucun asynchrone**.

## 🗓️ Votre déroulé

| Quand | À faire | Où dans la fiche |
|---|---|---|
| **Mardi 15h30-15h50** | Lecture croisée des cadrages M8-B1 de chaque membre + création du repo de groupe | — |
| **Mardi 15h50-16h05** | Lister les **3-5 divergences** entre vos cadrages | §1 |
| **Mardi 16h05-16h45** | **Trancher** chaque divergence : positions, décision, pourquoi | §1 |
| **Mercredi 9h00-9h30** | Retour d'expérience terrain sur l'IA agentique : notez ce qui servira à votre arbitrage « agents ? » | — |
| **Mercredi 9h30-10h00** | **5 arbitrages** : choix + raisons (≥ 1 chiffrée) + condition de changement d'avis, ou « non applicable » justifié | §2 |
| **Mercredi 10h00-11h00** | Architecture finale (Mermaid) + ce qu'on n'a pas mis, évaluation, déploiement & monitoring, conformité & sécurité, coûts | §3 à §7 |
| **Mercredi 11h00-11h15** | 5 questions probables + réponses, répartition de la parole, **commit final 11h15** | Annexe |
| **Mercredi 11h15-12h15** | **Restitution** : 20 min par groupe (12 min d'oral sur le schéma final + 8 min de questions). Pas de slides, **chaque membre parle** | — |

## 🧭 Ce que vous produisez

| # | Livrable | Fichier |
|---|---|---|
| 1 | **Fiche de décision** (3-4 pages **maximum**) — livrable principal : décisions de groupe, 5 arbitrages, architecture finale, évaluation, déploiement & monitoring, conformité & sécurité, coûts, questions prévues en annexe | `dossier_conception_TEMPLATE.md` → `dossier_conception.md` |
| 2 | README : qui a fait quoi + comment lire la fiche en 2 min | `README.md` |

Tout est **dans la fiche** : pas de fichiers séparés à recopier.

## ✅ Réussite

- Divergences **tranchées et argumentées** (négociation, pas union des cadrages).
- 5 arbitrages **tranchés ou non applicables** (justifiés) — pas de GenAI forcée par la grille.
- Archi **cohérente** avec les arbitrages (RAG non ⇒ pas de vector DB) et avec l'imprévu client de mardi.
- **Sobriété visible** : justifier **ce qu'on n'a PAS mis**.
- 5 questions **réalistes** préparées. À l'oral, chaque membre parle et le groupe tient sa décision.
- Commits de **chaque** membre. **Journal de bord** tenu.

## 📚 Ressources

Voir [`./ressources/`](./ressources/) — 5 mini-cours + `fiche_chiffrage.md` + `liens_officiels.md`.
