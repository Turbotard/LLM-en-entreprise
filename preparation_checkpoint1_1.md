# Checkpoint 1 — Sujet 1 : LLM en entreprise (RAG vs Fine-tuning vs Agents)

## Problématique

Quelle approche (RAG, fine-tuning, agents) offre le meilleur compromis fiabilité / coût / maintenabilité pour un LLM sur un corpus documentaire d'entreprise ?

## Hypothèses

| # | Hypothèse | Indicateur | Protocole |
|---|-----------|------------|-----------|
| H1 | Un RAG amélioré (rerank + citations) bat un RAG basique en fiabilité | % réponses correctes et sourcées | 30 questions golden set, comparaison A/B |
| H2 | Le fine-tuning ne se justifie que sur du contenu très spécialisé (jargon, formats atypiques) | Score qualité sur questions spécialisées vs génériques | Comparaison RAG vs fine-tuning sur les deux types |
| H3 | Un agent n'apporte pas de gain en Q&A documentaire simple, mais coûte plus cher et répond plus lentement | Latence, coût tokens, score qualité | Mêmes 30 questions, agent vs RAG |

## Sources primaires

| # | Source | Quoi | Lien |
|---|--------|------|------|
| 1 | Lewis et al. (2020) | Paper fondateur du RAG — NeurIPS | https://arxiv.org/abs/2005.11401 |
| 2 | Gao et al. (2024) | Survey RAG (chunking, reranking…) | https://arxiv.org/abs/2312.10997 |
| 3 | ARAGOG — Eibich (2024) | Benchmark techniques RAG avancées | https://arxiv.org/abs/2404.01037 |
| 4 | RAGAS — Es et al. (2024) | Framework évaluation RAG | https://arxiv.org/abs/2309.15217 |
| 5 | ReAct — Yao et al. (2023) | Paper fondateur agents LLM — ICLR | https://arxiv.org/abs/2210.03629 |
| 6 | OpenAI — Fine-tuning docs | Quand fine-tuner vs RAG/prompting | https://platform.openai.com/docs/guides/fine-tuning |
| 7 | LangChain — Docs officielles | Framework RAG + agents | https://docs.langchain.com |
| 8 | LlamaIndex — Docs officielles | Framework spécialisé RAG | https://docs.llamaindex.ai |
| 9 | Paper benchmark agents vs RAG | Benchmark agents vs RAG classique sur des tâches complexes | https://arxiv.org/html/2510.13910v1 |
| 10 | Paper hallucinations LLM, benchmark MTEB (embeddings) | Survey complet sur les hallucinations LLM (causes, détection, réduction) | https://arxiv.org/abs/2510.06265 |

## Contacts podcast
[CONTACTS-POUR-LES-INTERVIEWS.md](./Interviews/CONTACTS-POUR-LES-INTERVIEWS.md)