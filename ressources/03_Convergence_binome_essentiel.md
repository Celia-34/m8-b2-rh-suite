# Converger en groupe (binôme ou trio, 2-3 visions techniques) — Mini-cours

> Brief associé : M8-B2
> Durée de lecture : ~15 min
> Pré-requis : les cadrages M8-B1 de chaque membre du groupe
> *(nom de fichier historique « binome » : le mini-cours couvre binôme et trio)*

## Pourquoi cette techno ?

Vous étiez 2 ou 3 sur le **même client** en M8-B1, mais vous avez cadré
**différemment**. En M8-B2, vous devez produire **une seule** conception, en
1 h 15 le mardi. Converger n'est pas fusionner (coller les textes) ni s'aligner
par fatigue : c'est **négocier** chaque divergence et **trancher** avec une
raison. C'est une compétence pro réelle (CT9) — défendre, écouter, décider.

## Concepts clés

- **Convergence ≠ union** : on ne juxtapose pas les cadrages, on choisit.
- **Lister les divergences** : 3-5 points majeurs à trancher en priorité (famille
  de modèle, données à acquérir, KPI, qualification AI Act, lecture de l'imprévu
  client…).
- **Pour chaque divergence** : positions / **décision retenue + raison** → §1 de
  la fiche de décision.
- **Pas de compromis mou** : « on met les deux » est rarement la bonne réponse.
- **Spécificité du trio** : à trois, la majorité 2 contre 1 est tentante — mais
  un vote n'est pas un argument. Tranchez sur la **raison**, et donnez un rôle à
  chacun (animateur du temps, scribe de la fiche, avocat de la sobriété qui
  demande « et si on faisait plus simple ? »). Faites tourner les rôles le mercredi.
- **Répartir sans découper** : chacun rédige des sections, mais tout le groupe
  valide §1 et §2 ; sinon la fiche devient trois documents collés.
- **Désaccord sain** : challenger l'autre améliore la conception.

## Exemple minimal qui tourne

```markdown
| Divergence | Positions | Décision | Pourquoi |
|---|---|---|---|
| Seuil de revue humaine | A : 0.5 · B : 0.7 · C : 0.7 | 0.6 | charge de revue < 20 % des tickets ET précision > 85 % |
| Données personnelles | A : suppression · B : pseudonymisation | pseudonymisation | garde le signal utile au tri |
```

## Exercice guidé

En groupe, mardi 15h30 :
1. 20 min : chacun lit les cadrages des autres, note ce qui diffère du sien.
2. 15 min : mettez en commun et gardez les 3-5 divergences qui changent la conception.
3. 40 min : pour chacune, chaque membre argumente (2 min max), puis **tranchez**
   et remplissez §1.

*Solution attendue* : un tableau §1 de 3-5 lignes, chaque décision justifiée
par une raison (pas « on a voté »).

## Pièges fréquents

| Piège | Conséquence |
|---|---|
| Coller les cadrages | Conception incohérente |
| Compromis mou (« les deux ») | Sur-engineering / indécision |
| Trancher par vote 2 contre 1 sans argument | Choix non défendable à l'oral |
| Un membre rédige tout | Les autres ne savent pas défendre la fiche |
| Éviter le désaccord | On rate l'amélioration mutuelle |

| Symptôme | Cause probable |
|---|---|
| Fiche contradictoire | Union au lieu de convergence |
| Archi qui « met tout » | Compromis mou |
| Un membre muet à la restitution | Rôles et sections non répartis |
| Restitution décousue | Pas de décision commune claire en §1 |

## Pour aller plus loin

- Cf. M6-B2 (coordination groupe) — collaboration à plus grande échelle.
- Pair programming (Fowler) : https://martinfowler.com/articles/on-pair-programming.html

## Vérification (checklist apprenant)

- [ ] On a listé 3-5 divergences majeures.
- [ ] Chaque divergence est **tranchée** avec une raison (pas « on verra », pas « on a voté »).
- [ ] §1 de la fiche trace positions / décision / pourquoi.
- [ ] Pas de compromis mou (« on met les deux »).
- [ ] Chaque membre a un rôle et des sections, et peut défendre toute la fiche.

> 💡 **Récap — Convergence en groupe** : convergence ≠ union ≠ compromis mou ≠ vote : on **négocie** et on **tranche** chaque divergence avec une raison, tracée en §1. En trio, des rôles tournants (temps, scribe, avocat de la sobriété) évitent qu'un membre porte tout.

### À retenir

- **Chiffrer** plutôt qu'affirmer : un nombre vaut mieux qu'un adjectif.
- **Sobriété** : recommander le plus simple qui résout le besoin, et **dire ce qu'on écarte**.
- Tracer ses **choix** et leur **raison** — c'est ce qui se défend en restitution.
