# 04_Demos_Attendues_Par_Sujet.md
## Démonstrations attendues — MVT LeadDev 2026

### Règles communes (toutes les démos)
- Reproductible via Docker/Makefile.
- Métriques + benchmark.
- Comparaison A/B.
- **1 test qui rate** + analyse + correctif OU décision assumée.
- Résultats versionnés dans `/evidence/results/`.

---

## Sujet 1 — LLM : RAG vs Fine-tuning vs Agents
### Démo
Mini assistant sur corpus (docs publics ou “internes fictifs”) :
- Mode A : RAG baseline
- Mode B : RAG amélioré (rerank, chunking, citations/grounding)
- Option : agent OU fine-tuning léger (si pertinent)

**Dataset** : corpus 30–100 docs + 30 questions “golden set”.  
**Métriques** : grounded answers (citations correctes), score exactitude (rubric), latence, coût estimé.  
**Benchmark** : A vs B sur golden set.  
**Test qui rate** : question info absente / contradictions → analyse retrieval + abstention/correctif.

---

## Sujet 2 — Platform Engineering / IDP
### Démo
Golden path minimal pour une API :
- scaffolding,
- CI standard,
- build+scan+déploiement (test env),
- observabilité minimale.

**Métriques** : temps onboarding, lead time change trivial, taux échec pipeline, temps rollback (simulé).  
**Benchmark** : manuel vs golden path.  
**Test qui rate** : non-conformité (secret absent, config invalide) → blocage + feedback + amélioration.

---

## Sujet 3 — Supply chain security (SBOM/SLSA/signature)
### Démo
Pipeline CI qui produit :
- artefact buildé,
- SBOM,
- signature,
- attestation/provenance,
- vérification en release.

**Métriques** : overhead pipeline, couverture SBOM, vulnérabilités détectées (si scan).  
**Benchmark** : baseline vs sécurisé.  
**Test qui rate** : artefact non signé/provenance invalide → refus + analyse contournements + policy.

---

## Sujet 4 — Observabilité OpenTelemetry
### Démo
Petite app instrumentée (2 services si possible) :
- traces,
- logs corrélés (trace_id),
- métriques (latence, taux erreur),
- dashboard/queries.

**Métriques** : temps diagnostic incident (exercice), volume/cardinalité, overhead.  
**Benchmark** : sans OTel vs avec OTel sur incident simulé.  
**Test qui rate** : timeout DB / retry storm → sans traces opaque, avec traces cause visible.

---

## Sujet 5 — WebAssembly côté serveur (WASI, plugins)
### Démo
Système de plugins :
- host backend charge plugin wasm
- exécute transformation/validation
- sandbox + limites (CPU/mémoire) si possible.

**Métriques** : latence native vs wasm, CPU/RAM, cold start.  
**Benchmark** : natif vs wasm sur mêmes inputs.  
**Test qui rate** : plugin malveillant/buggy (boucle, mémoire, accès interdit) → timeout/quota + analyse sandbox.

---

## Sujet 6 — Confidential Computing (TEE)
### Démo
Traitement données sensibles :
- modèle de menace écrit,
- chiffrement côté client,
- exécution protégée (réelle si possible, sinon simulation honnête),
- preuve de non-exposition (au moins conceptuelle + logs).

**Métriques** : overhead perf, complexité d’intégration, surface d’attaque restante.  
**Benchmark** : standard vs “confidential”.  
**Test qui rate** : tentative inspection (dump/logs/debug) → comparaison TEE vs non-TEE + analyse menaces restantes.

