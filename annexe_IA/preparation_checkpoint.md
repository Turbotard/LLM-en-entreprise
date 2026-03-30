# Annexe IA — Usage de l'IA dans le projet

## 1. Préparation Checkpoint 1 (30/03/2026)

### Prompts

**Prompt 1 — Structuration des idées**

Je bosse sur un MVT en master LeadDev sur "LLM en entreprise : RAG vs Fine-tuning vs Agents". J'ai des idées de problématique et d'hypothèses mais j'arrive pas à les formuler de façon testable. Aide moi à les structurer en tableau markdown avec pour chaque hypothèse ce qu'on mesure et comment on teste. Dis moi aussi si mes hypothèses tiennent la route ou si elles sont trop vagues / pas falsifiables.
Ma problématique : en gros quand t'es lead dev et que tu veux coller un LLM sur tes docs d'entreprise, tu pars sur quoi ? RAG, fine-tuning, agents ? c'est quoi le plus fiable sans que ça explose en coût et en maintenance ?
Mes hypothèses :
- un RAG avec du reranking et des citations c'est mieux qu'un RAG basique
- le fine-tuning ça vaut le coup que si t'as du contenu vraiment technique sinon le RAG suffit
- les agents pour du Q&A sur des docs c'est overkill, plus cher et plus lent pour rien


**Prompt 2 — Sources**

Quelles sont les sources primaires les plus reconnues et fiables sur RAG, fine-tuning et agents LLM ? Je veux pas des articles de blog, je veux des papers publiés en conférence, des docs officielles, des benchmarks. Pour chaque source dis moi pourquoi elle fait référence et dans quelle conférence elle a été acceptée si c'est un paper.

### Ce que j'ai gardé

- La structure en tableaux pour la lisibilité
- Les sources arXiv (Lewis, RAGAS, ReAct, ARAGOG) vérifiées manuellement
- Les docs officielles LangChain/LlamaIndex

### Ce que j'ai modifié

- La problématique et les hypothèses viennent de nos idées mais l'IA a reformulé pour que ce soit plus clair et structuré
- Le fond a été validé avec le groupe lors du point du 30/03
- Les indicateurs de chaque hypothèse ont été précisés ensemble

### Ce que j'ai jeté

- L'IA proposait une H4 sur la maintenabilité RAG vs fine-tuning, pas gardée parce qu'on peut pas la tester sans POC long terme
- 2 sources proposées étaient des articles de blog, remplacées par des sources primaires trouvées par le groupe

### Limites

- L'IA formule les hypothèses de façon trop "propre", on a dû vérifier qu'elles restaient testables dans notre cadre
- Les sources qu'elle propose ont l'air solides mais faut vérifier si le paper a bien été accepté en conférence
