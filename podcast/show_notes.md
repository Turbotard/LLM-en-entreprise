# Show notes — Podcast MVT LLM en entreprise

**Titre :** LLM en entreprise, RAG, fine-tuning et agents, le point de vue d'un établissement public
**Invité :** Mohand Makhoukhene, chargé de projet au CIG (fonction publique territoriale)
**Date :** 24 juin 2026 
**Durée :** environ 38 minutes

## 5 takeaways

1. Sur un corpus juridique, le RAG avec re-ranking est plus fiable que le RAG basique, parce qu'il hybride recherche sémantique et recherche lexicale et retrouve les références exactes d'articles de loi.
2. Le fine-tuning d'un gros modèle se chiffre à l'ordre du million d'euros et demande une infra GPU lourde, hors de portée d'un établissement public.
3. Le déclencheur du fine-tuning est double, un RAG insuffisant plus un volume important de données hétérogènes avec un vocabulaire très spécifique, par exemple un cabinet d'avocats.
4. Un agent sert à automatiser des tâches multi-étapes, traduction d'e-mails ou compte rendu de réunion, pas à mieux répondre à une question documentaire simple.
5. La souveraineté de la donnée structure toute la stratégie, charte IA, anonymisation des prompts, modèles open source déployés en interne via Ollama pour éviter le Shadow IA.

## 3 timestamps

- [08:06] Fonctionnement d'un RAG, chunking, embedding, base vectorielle
- [12:23] RAG basique contre RAG re-ranking, fiabilité sur les textes de loi
- [19:14] Coût et maintenabilité du fine-tuning

## 5 liens

- ARAGOG (Eibich, 2024), source primaire, https://arxiv.org/abs/2404.01037
- Ovadia et al. (2024), source primaire, https://arxiv.org/abs/2312.05934
- Ferrazzi et al. (2026), source primaire, https://arxiv.org/abs/2601.07711
- ReAct (Yao et al., 2023), source primaire, https://arxiv.org/abs/2210.03629
- RAGAS (Es et al., 2024), source primaire, https://arxiv.org/abs/2309.15217

## Ce que ça change dans H1, H2, H3

H1 est confirmée sur le terrain par un RAG re-ranking développé sur un corpus juridique français, là où nos sources étaient surtout anglaises et généralistes.

H2 est confirmée mais recadrée, le vrai frein au fine-tuning étant d'abord le coût et les ressources, pas seulement la spécialisation du contenu.

H3 est soutenue sur le plan conceptuel, l'agent servant à automatiser et non à mieux répondre, mais sans confirmation chiffrée du surcoût, qui reste appuyé sur la littérature.
