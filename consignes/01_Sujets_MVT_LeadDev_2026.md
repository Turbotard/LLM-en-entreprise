# 01_Sujets_MVT_LeadDev_2026.md
## MVT (Mémoire de Veille Technologique) — LeadDev M1/M2I — 2026
**Organisation :** 18 étudiants → 6 groupes de 3 → 6 sujets (1 groupe = 1 sujet).  
**Période :** démarrage 15/01/2026.  
**Journées de suivi (avec l’intervenant) :** 31/03/2026, 17/06/2026.  
**Soutenance finale :** 01/07/2026.

### Deadlines
- **Podcast / Interview : 01/06/2026**
- **Document MVT + Dossier de preuves : 10/06/2026 23:59**
- **Démo + Slides + accès Git : le 01/07/2026 (jour de soutenance)**

---

## Règle de choix des sujets
- 6 sujets ci-dessous, **un seul groupe par sujet**.
- Attribution : *premier groupe qui dépose une “fiche sujet” (1 page) sur le repo* (titre + problématique + 3 hypothèses + 10 sources primaires pressenties + cible(s) podcast) → sujet réservé.
- Si conflit le même jour : tirage au sort.

---

## Sujet 1 — LLM en entreprise : RAG vs Fine-tuning vs “Agents”
### Angle LeadDev
Construire une solution LLM **fiable** (qualité/références/latence/coût) sans fabriquer une bombe de maintenance.
### Questions possibles
- À partir de quel seuil de données/problèmes le fine-tuning devient rationnel ?
- RAG : comment mesurer retrieval/grounding et réduire l’hallucination ?
- Agents : où est la valeur réelle vs “démo show” ?
### Interview (types d’invités faciles à trouver)
- Équipe data/IA en entreprise.
- Chercheur/doctorant IA (université, labo).
- Intégrateur/éditeur IA (ESN/outilleur).
### Sources primaires typiques
- Papers RAG/evaluation, specs/Docs officielles, repos officiels, benchmarks publiés.

---

## Sujet 2 — Platform Engineering / Internal Developer Platform (IDP)
### Angle LeadDev
Améliorer le flux dev→prod (productivité, fiabilité, conformité) sans transformer DevOps en police.
### Questions possibles
- Quels indicateurs prouvent la valeur (lead time, change failure rate, MTTR, etc.) ?
- Quels “golden paths” minimum (CI templates, secrets, env preview…) ?
- Où s’arrête la plateforme et où commence l’équipe produit ?
### Interview
- Platform engineer, SRE, Staff/Principal engineer, DevOps lead.
### Sources primaires
- DORA, docs/outils (Backstage, Crossplane, Terraform…), CNCF, OTel.

---

## Sujet 3 — Sécurité supply chain : SBOM, SLSA, signature, provenance
### Angle LeadDev
Après un “npm install”, comment éviter la compromission bête et méchante ?
### Questions possibles
- Protocole minimal réaliste (SBOM + signature + policy) ?
- ROI : temps, incidents évités, conformité.
- Comment mesurer une réduction de risque ?
### Interview
- RSSI, AppSec, DevSecOps, CERT interne/prestataire.
### Sources primaires
- SLSA, Sigstore, CycloneDX/SPDX, docs officielles, advisories.

---

## Sujet 4 — Observabilité moderne : OpenTelemetry + logs/metrics/traces corrélés
### Angle LeadDev
Ce n’est pas “on a Grafana”. C’est “on résout un incident vite et bien”.
### Questions possibles
- Quelles métriques/traces sont réellement actionnables ?
- Instrumentation “minimum viable” ?
- Coûts (cardinalité, sampling, stockage) vs valeur ?
### Interview
- SRE/Ops, dev backend, consultant observabilité.
### Sources primaires
- Spéc OpenTelemetry, docs Prometheus/Tempo/Jaeger, patterns SRE.

---

## Sujet 5 — WebAssembly côté serveur : WASI, plugins, sandboxing
### Angle LeadDev
Isoler du code, porter des plugins, exécuter en sandbox : promesse énorme, pièges énormes.
### Questions possibles
- Performance/latence vs natif ?
- Sandbox réelle ou marketing ?
- Cas d’usage crédibles (plugins, edge, multi-tenant) ?
### Interview
- Dev runtime/infra, équipe qui maintient un plugin system.
### Sources primaires
- Specs WASI, repos runtimes (Wasmtime/Wasmer), benchmarks.

---

## Sujet 6 — Confidential Computing : enclaves/TEE + données sensibles
### Angle LeadDev
Traiter des données sensibles sans que l’infra puisse les lire : possible, mais pas magique.
### Questions possibles
- Menaces couvertes vs menaces restantes ?
- Coût/complexité d’exploitation.
- Comment prouver le gain de sécurité ?
### Interview
- Architecte sécurité, cloud provider, équipe crypto appliquée, chercheur.
### Sources primaires
- Docs TEE, publications sécurité, threat models, repos d’exemples.
