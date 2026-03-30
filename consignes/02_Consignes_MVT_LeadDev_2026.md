# 02_Consignes_MVT_LeadDev_2026.md
## Consignes officielles — MVT + Dossier de preuves + Démo (LeadDev M1/M2I)

### Objectif (clair)
Vous ne me vendez pas une “tendance”. Vous **prouvez** quelque chose :
- hypothèses **falsifiables**,
- **sources primaires**,
- protocole **reproductible**,
- résultats **mesurés**,
- défense **argumentée**.

### IA (autorisé, mais tracé)
L’IA est **autorisée**. Le copier-coller déguisé, non.
- Vous devez fournir une **annexe IA** avec :
  - vos **prompts** (copiés-collés),
  - les extraits utiles de réponses,
  - ce que vous avez **gardé / jeté**,
  - et **pourquoi** (justification technique, qualité, contraintes, cohérence).
- Sans annexe IA : la partie “démarche” est considérée **non démontrée** (voir grille de notation).

---

## 1) Livrables & Dates
### A. Podcast / Interview (obligatoire)
- **À rendre : 01/06/2026**
- Format :
  - **Au moins 1 invité** (chercheur/pro en lien direct avec le sujet).
  - Durée recommandée : **15 à 25 min**.
  - Audio : `.mp3` (128–192 kbps) + `show_notes.md`.
  - Le podcast doit alimenter votre MVT : **3 citations courtes max** + analyse (pas du name-dropping).
- Bonus utile : transcript auto + nettoyage partiel.

### B. Document MVT + Dossier de preuves
- **À rendre : 10/06/2026 23:59**
- Format :
  - `MVT.pdf` (export) + sources en Markdown dans le repo.
  - Dossier de preuves dans le repo (`/evidence/`).

### C. Soutenance finale + Démo + Slides + Git accessible
- **01/07/2026**
- Slides : `slides.pdf` ou `pptx`.
- Repo : lien + tag/release `v1.0-soutenance`.

---

## 2) Structure obligatoire du document (MVT)
> Le MVT doit être lisible. Mais c’est le **dossier de preuves** qui fait foi.

### 2.1 Page 1 — Synthèse (MAX 1 page)
Contenu minimum :
- Problématique (1 paragraphe).
- 3 hypothèses (H1/H2/H3) + ce que vous cherchez à prouver.
- Résultat en une phrase par hypothèse (validée / infirmée / incertaine).
- Reco finale (décision) : “Si j’étais LeadDev, je ferais X / je ne ferais pas Y, parce que…”.

### 2.2 Table Hypothèses (obligatoire)
Format imposé :

| Hypothèse | Indicateur mesurable | Protocole de test | Résultat | Niveau de confiance |
|---|---|---|---|---|

Règles :
- Une hypothèse = testable = réfutable.
- “Niveau de confiance” doit être justifié (taille d’échantillon, biais, limites).

### 2.3 Table Claims → Sources (obligatoire)
Format imposé :

| Claim (affirmation) | Source primaire | Pourquoi crédible | Limites / biais |
|---|---|---|---|

Règles :
- “Source primaire” = paper, RFC/spec, doc officielle, repo officiel, standard, benchmark publié.
- Vous pouvez citer des secondaires, mais **elles ne remplacent jamais** la primaire.

### 2.4 Contre-arguments (obligatoire)
- **3 objections sérieuses** (pas des hommes de paille).
- Pour chaque objection :
  - réponse,
  - et **ce qui vous ferait changer d’avis** (condition de falsification).

### 2.5 Conclusion opérationnelle
- Une décision (même si c’est “on ne sait pas encore, donc on ne déploie pas”).
- Un plan de suite : prochain test à faire, risque à réduire, etc.

---

## 3) Dossier de preuves (obligatoire)
Le dossier de preuves doit permettre à un tiers de **reproduire** votre résultat.

### 3.1 Reproductibilité
À fournir :
- Script de reproduction : `Dockerfile` + `docker compose` **ou** `Makefile`.
- Données/inputs : dataset, jeux d’entrées, générateur, ou mocks.
- Métriques : définition + comment elles sont collectées.
- Benchmark : au moins 2 configurations comparées (A vs B).

### 3.2 “Un test qui rate” (obligatoire)
Vous devez montrer :
- 1 edge-case qui casse votre système (ou révèle un risque majeur),
- pourquoi ça rate (hypothèse causale),
- correctif **ou** décision assumée (contournement/changement de scope), avec justification.

### 3.3 Structure repo recommandée
```
/README.md
/mvt/                 # mémoire (md) + export pdf
/evidence/            # preuves reproductibles
  /scripts/
  /data/              # ou générateur
  /results/
  /notebooks/         # optionnel
/adr/                 # décisions structurantes (1 page max)
/journal/             # 10 entrées datées
/podcast/             # audio + show notes
/src/                 # proto
/ai/                  # annexe IA (prompts + choix gardés/jetés)
```

---

## 4) Git : exigences minimales
### 4.1 Commits
- Commits réguliers (pas 1 commit la veille).
- Messages lisibles.

### 4.2 Issues
- Minimum : 10 issues par groupe.
- Chaque issue a une conclusion (done / wontfix / blocked).

### 4.3 ADR (Architecture Decision Records)
- 1 décision = 1 ADR max 1 page.
- Minimum : 5 ADR (stack, protocole de test, métriques, architecture, sécurité/risques).
- Format : Contexte / Décision / Alternatives / Conséquences.

### 4.4 Journal de veille (10 entrées datées)
Format imposé :
- Date
- Ce que j’ai lu (avec lien/source primaire)
- Ce que j’ai compris (résumé perso)
- Ce que ça change dans notre proto (action/décision)

---

## 5) IA : annexe obligatoire
Fichier `ai/ai_usage.md` :
- Prompts (copiés-collés).
- Résultats utiles (extraits).
- **Décision** : gardé/jeté + pourquoi (qualité, compat, sécurité, perf, coût, maintenabilité).
- Limites/risques : où l’IA peut vous induire en erreur sur votre sujet.

---

## 6) Soutenance : attentes
- Présentation + démo + questions.
- Slides = support, pas roman.
- Démo :
  - tourne sur machine neutre (ou docker),
  - montre métriques + benchmark + test qui rate,
  - montre le dossier de preuves dans le repo.

---

## 7) Jours de suivi (obligatoire)
### 31/03/2026 — Checkpoint 1
À montrer :
- Sujet verrouillé + problématique.
- H1/H2/H3 formulées.
- 10 sources primaires shortlist.
- Plan podcast + 2 contacts sollicités.
- Proto squelette + scripts de repro démarrés.

### 17/06/2026 — Checkpoint 2
À montrer :
- Podcast rendu (ok).
- MVT quasi final + tableaux complets.
- Benchmarks exécutés + résultats.
- Edge-case identifié + analyse.
- Repo propre + ADR + journal complété.




Lien des consignes : https://docs.google.com/spreadsheets/d/1r4NhKrHoXoEDQ8BkNVyovwYAWRQChVH9/edit?gid=1009551376#gid=1009551376