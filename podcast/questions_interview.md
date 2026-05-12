# Questions — Interview Podcast 
**Sujet : LLM en entreprise — RAG vs Fine-tuning vs Agents**

---

## Introduction 

- Pouvez-vous vous présenter et décrire votre rôle vis-à-vis des LLM ?
- Depuis quand votre équipe expérimente-t-elle des LLM en production ?

---

## RAG 

- Concrètement, comment utilisez-vous le RAG sur vos corpus documentaires internes ?
- Avez-vous comparé un RAG basique à des techniques avancées (reranking, citations) ? Qu'est-ce que ça change vraiment en fiabilité ?
- Comment mesurez-vous qu'une réponse est "fiable" — vous avez des métriques maison ou vous utilisez des frameworks comme RAGAS ?
- L'hallucination, c'est votre principal problème ou il y en a d'autres ?

---

## Fine-tuning 

- Est-ce que vous avez fine-tuné des modèles ? Si oui, sur quel type de contenu et pourquoi le RAG seul ne suffisait pas ?
- À quel moment vous vous dites "là il faut fine-tuner" — c'est quoi le signal ?
- Le coût et la maintenance d'un modèle fine-tuné, c'est gérable dans une grande structure ?

---

## Agents 
- Vous utilisez des agents LLM en production, ou c'est encore expérimental ?
- Sur du Q&A documentaire simple, est-ce qu'un agent apporte vraiment quelque chose par rapport à un RAG bien réglé ?
- La latence et le coût des agents, c'est un frein réel chez vous ?

---

## Vision LeadDev 

- Si un dev doit construire une solution LLM fiable aujourd'hui pour un corpus entreprise, vous lui conseillez quoi comme stack de départ ?
- C'est quoi la bombe de maintenance que vous avez failli poser — ou que vous avez vue en démo et jamais en prod ?
- Dans 2 ans, RAG ou agents, qui gagne ?


Base Claude avec reformulation Humaine (sert de contexte essentiellement)