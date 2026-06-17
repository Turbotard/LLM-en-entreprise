# Annexe IA — Vérification des sources et finalisation du MVT

Cette section complète `ai/preparation_checkpoint.md` (Checkpoint 1). Elle documente une session d'assistance IA menée en juin 2026, dont l'objectif était d'auditer le MVT face aux consignes, de vérifier chaque hypothèse contre ses sources primaires, de corriger les erreurs détectées, et de produire des livrables manquants (ADR). Les prompts ci-dessous sont reformulés pour la lisibilité ; l'esprit est conservé.

---

## 1. Audit du MVT face aux consignes

**Prompt.** « D'après le PDF du MVT et les consignes, dis-moi ce qui manque, sachant que c'est un mémoire de M1. »

**Ce que l'IA a produit.** Une analyse d'écart classée par gravité, qui a identifié :
- conclusion vide (page dédiée sans contenu) ;
- colonnes *Résultat* et *Niveau de confiance* vides dans la synthèse et la table hypothèses ;
- podcast non intégré au mémoire (aucune citation terrain dans les résultats) ;
- 0 ADR sur les 5 exigés ;
- environ 1 entrée de journal de veille sur les 10 exigées, et pas au format imposé ;
- annexe IA ne couvrant que le Checkpoint 1 ;
- rappel que la deadline réelle du pack est le 20/06 (et non les anciennes dates 01/06 et 10/06).

**Décision.** Gardé comme feuille de route de fin de projet. Point de vigilance soulevé par l'IA et retenu : certains chiffres du mémoire (« +15 à +30 % », « x3 à x10 ») étaient affirmés sans source vérifiable.

---

## 2. Vérification de H1 (RAG amélioré vs basique)

**Prompt.** « En consultant les sources donne le bon indicateur et les chiffres réels. »

**Sources vérifiées.** ARAGOG (Eibich et al., 2024, arXiv:2404.01037), texte intégral ; RAGAS (Es et al., 2024, arXiv:2309.15217).

**Extraits utiles retenus.**
- ARAGOG mesure la *précision de récupération* (0–1) et la *similarité de réponse* (0–5), sur 107 questions, corpus de 423 papers, GPT-3.5-turbo, 10 runs, tests ANOVA + Tukey.
- Gains réels en précision : reranking par LLM environ +0,05, HyDE environ +0,065, combinaison HyDE + LLM rerank environ +0,075. MMR et Cohere rerank : non significatifs. Le chunking *Sentence Window* est le plus gros levier (environ +0,10).
- ARAGOG note explicitement que ces techniques ajoutent des appels LLM, donc plus de latence et de coût.

**Décision.**
- Gardé : H1 confirmée, mais pour les bonnes techniques seulement.
- Modifié : indicateur reformulé en « précision de récupération » (ARAGOG ne mesure ni l'exactitude vs vérité-terrain ni les citations).
- Jeté : le chiffre « +15 à +30 % », introuvable dans la source ; remplacé par +0,05 à +0,10. Jetée aussi l'affirmation « coût en tokens quasi nul », contredite par la source.

---

## 3. Vérification de H2 (fine-tuning vs RAG)

**Sources vérifiées.** Ovadia et al. (2024, arXiv:2312.05934), texte intégral ; documentation OpenAI (Model Optimization).

**Extraits utiles retenus.**
- Métrique : exactitude sur QCM factuels (sous-ensembles MMLU + une tâche « current events »), modèles Mistral, Llama2 et Orca2 7B.
- Sur la connaissance nouvelle, le RAG porte l'exactitude de 0,48 à 0,88 (Mistral), là où le fine-tuning non supervisé ne fait que 0,48 à 0,50, et peut même dégrader le modèle (Llama2 : 0,35 à 0,22).

**Décision.**
- Gardé : H2 confirmée pour la connaissance (RAG bat largement le fine-tuning non supervisé).
- Modifié : indicateur reformulé en « connaissance existante vs nouvelle » (et non « spécialisé vs générique »). Précisé que la moitié « fine-tuner pour le style et les formats » repose seulement sur la doc OpenAI, donc non mesurée.
- Jeté : l'affirmation de la table Sources selon laquelle Ovadia teste « uniquement des modèles OpenAI ». Faux : il teste Mistral, Llama2 et Orca2 (modèles ouverts).

---

## 4. Correction de H3 (agents vs RAG) — décision majeure

**Prompts successifs.** « Le bon indicateur, c'est temps/coût/qualité, trouve une source qui fait vraiment cette comparaison. » Puis : « D'où sort le x3 à x10 et est-il crédible ? »

**Problème détecté par l'IA.** La source citée pour H3, RAGCap-Bench (Lin et al., 2025, arXiv:2510.13910), ne mesure ni le coût en tokens, ni la latence, ni un comparatif agent vs RAG. Après lecture du texte intégral, ses seules métriques sont Exact Match et F1 sur 255 QCM ; le seul multiplicateur du papier est « environ 50× plus rapide » (le benchmark vs une évaluation agentique complète), sans rapport avec le coût d'un agent. Le « x3 à x10 » lui était donc attribué à tort.

**Origine réelle du chiffre.** Billets industriels de 2025–2026 (MarsDevs, repris par d'autres). C'est de la littérature grise, pas une source primaire.

**Source de remplacement trouvée.** Ferrazzi, Cvjeticanin, Piraccini & Giannuzzi (2026), *Is Agentic RAG worth it? An experimental comparison of RAG approaches*, arXiv:2601.07711 (Industry Day, LREC 2026). Étude qui compare directement RAG amélioré et agentique sur FIQA, NQ, FEVER, CQADupStack, en mesurant tokens, latence et qualité.

**Extraits utiles retenus.**
- Surcoût mesuré : environ 3,3× plus de tokens en entrée, 1,9× en sortie, 1,5× plus de temps, jusqu'à 3,6× de coût total.
- Qualité nuancée : aucun des deux paradigmes n'est universellement supérieur. L'agent aide au routage d'intention et à la reformulation, mais perd sur le reranking. Conclusion des auteurs : un RAG amélioré bien optimisé peut égaler ou dépasser l'agentique tout en restant plus efficace.

**Décision.**
- Gardé : Ferrazzi et al. comme source primaire de H3.
- Modifié : verdict H3 ramené de « confirmée » à « partiellement confirmée », confiance « moyenne ». Formulation adoucie de « pas de gain » vers « ne bat pas systématiquement un RAG amélioré bien réglé ».
- Jeté : RAGCap-Bench comme source du coût ; le « x3 à x10 » comme résultat mesuré (conservable uniquement comme estimation industrielle étiquetée).

---

## 5. Synthèse finale des trois hypothèses

Indicateurs, résultats et niveaux de confiance recalés sur les sources :

- **H1** — Indicateur : précision de récupération. Résultat : confirmée pour les bonnes techniques (+0,05 à +0,10). Confiance : moyenne.
- **H2** — Indicateur : exactitude sur QCM factuels (connaissance existante vs nouvelle). Résultat : confirmée pour la connaissance (RAG environ +0,40 vs fine-tuning environ +0,02). Confiance : moyenne.
- **H3** — Indicateur : coût en tokens, latence, qualité. Résultat : partiellement confirmée (environ 3,3× tokens, 1,5× temps, jusqu'à 3,6× coût ; qualité non systématiquement supérieure). Confiance : moyenne.

Protocole pour les trois : analyse de sources primaires et de benchmarks publiés, sans mesure maison.

