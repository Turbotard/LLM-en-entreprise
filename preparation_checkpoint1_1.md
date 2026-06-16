# Checkpoint 1 — Sujet 1 : LLM en entreprise (RAG vs Fine-tuning vs Agents)

## Problématique

Quelle approche (RAG, fine-tuning, agents) offre le meilleur compromis fiabilité / coût / maintenabilité pour un LLM sur un corpus documentaire d'entreprise ?

## Hypothèses

| # | Hypothèse | Indicateur | Protocole |
|---|-----------|------------|-----------|
| H1 | Un RAG amélioré (rerank + citations) bat un RAG basique en fiabilité | % de réponses correctes et sourcées | 30 questions de référence, comparaison A/B |
| H2 | Le fine-tuning ne se justifie que sur du contenu très spécialisé (jargon, formats atypiques) | Score de qualité sur questions spécialisées vs génériques | Comparaison RAG vs fine-tuning sur les deux types |
| H3 | Un agent n'apporte pas de gain en Q&A documentaire simple, mais coûte plus cher et répond plus lentement | Latence, coût en tokens, score de qualité | Mêmes 30 questions, agent vs RAG |


## Sources primaires

| # | Source | Quoi | Lien |
|---|--------|------|------|
| 1 | Lewis et al. (2020) | Article fondateur du RAG — NeurIPS | https://arxiv.org/abs/2005.11401 |
| 2 | Gao et al. (2024) | Revue de littérature RAG (découpage, réordonnancement…) | https://arxiv.org/abs/2312.10997 |
| 3 | ARAGOG — Eibich (2024) | Banc d'essai des techniques RAG avancées | https://arxiv.org/abs/2404.01037 |
| 4 | RAGAS — Es et al. (2024) | Cadre d'évaluation RAG | https://arxiv.org/abs/2309.15217 |
| 5 | ReAct — Yao et al. (2023) | Article fondateur des agents LLM — ICLR | https://arxiv.org/abs/2210.03629 |
| 6 | OpenAI — Documentation optimisation de modèle | Quand fine-tuner vs RAG/prompting | https://platform.openai.com/docs/guides/model-optimization |
| 7 | LangChain — Documentation officielle | Cadre RAG + agents | https://docs.langchain.com |
| 8 | LlamaIndex — Documentation officielle | Cadre spécialisé RAG | https://developers.llamaindex.ai/python/framework |
| 9 | RAGCap-Bench — Lin et al. (2025) | Évaluation fine des capacités des systèmes RAG agentiques | https://arxiv.org/abs/2510.13910 |
| 10 | Alansari & Luqman (2025) | Revue complète sur les hallucinations des LLM (causes, détection, atténuation) | https://arxiv.org/abs/2510.06265 |
| 11 | Ovadia et al. (2024) | RAG vs fine-tuning pour l'injection de connaissances — EMNLP | https://arxiv.org/abs/2312.05934 |

## Contacts podcast

[CONTACTS-POUR-LES-INTERVIEWS.md](./Interviews/CONTACTS-POUR-LES-INTERVIEWS.md)
