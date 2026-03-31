Lu. Voici ce que c'est :

  ---
  Paper : RAGCap-Bench — arXiv:2510.13910v1 (15 oct. 2025)
  Auteurs : Jingru Lin, Chen Zhang, Stephen Y. Liu, Haizhou Li (NUS + CUHK Shenzhen)

  En résumé

  Un benchmark qui évalue les LLMs au niveau des étapes intermédiaires d'un système RAG agentique, pas juste la réponse finale.

  Pourquoi c'est pertinent pour ton sujet

  Les systèmes RAG classiques souffrent de : raisonnement superficiel, accès limité aux données en temps réel, mauvaise intégration du contexte. Le RAG agentique donne au LLM un
  rôle d'agent : il planifie, cherche, raisonne, affine son plan, itère.

  Les 4 capacités testées dans le benchmark

  ┌─────────────────────┬─────────────────────────────────────────────────────────────────────────────────────────┐
  │      Capacité       │                                    Ce que ça mesure                                     │
  ├─────────────────────┼─────────────────────────────────────────────────────────────────────────────────────────┤
  │ Planning            │ Décomposer une question, ajuster le plan au fil des recherches (convergent / divergent) │
  ├─────────────────────┼─────────────────────────────────────────────────────────────────────────────────────────┤
  │ Evidence Extraction │ Identifier les sources pertinentes parmi le bruit                                       │
  ├─────────────────────┼─────────────────────────────────────────────────────────────────────────────────────────┤
  │ Grounded Reasoning  │ Raisonner fidèlement à ce que les sources disent (pas halluciner)                       │
  ├─────────────────────┼─────────────────────────────────────────────────────────────────────────────────────────┤
  │ Noise Robustness    │ Résister aux sources peu fiables / trompeuses                                           │
  └─────────────────────┴─────────────────────────────────────────────────────────────────────────────────────────┘

  Résultat clé

  Les modèles "slow-thinking" (ex. DeepSeek-R1, o3) qui réussissent mieux sur RAGCap-Bench obtiennent aussi de meilleurs résultats end-to-end — preuve que les capacités
  intermédiaires prédisent la qualité finale.

  ---
  Ce que tu dois en faire : c'est une source primaire directement utilisable pour H2 (mesurer retrieval/grounding et réduire l'hallucination). Tu as besoin qu'on en parle
  davantage ou tu veux déjà créer une entrée de journal de veille ?