# ADR-003 — Source de validation de H3

## Contexte
H3 était étayée par RAGCap-Bench, qui ne mesure ni coût ni latence. Le chiffre x3 à x10 lui était attribué à tort.

## Décision
Fonder H3 sur Ferrazzi et al. (2026), « Is Agentic RAG worth it? » (arXiv:2601.07711), qui compare RAG amélioré et agentique en coût, latence et qualité.

## Alternatives
Garder RAGCap-Bench reformulé, ou sourcer le x3 à x10 sur des blogs, écartées car inadaptée ou non primaire.

## Conséquences
H3 passe à partiellement confirmée avec des chiffres mesurés, environ 3,3 fois les tokens et 1,5 fois le temps. Confiance moyenne.
