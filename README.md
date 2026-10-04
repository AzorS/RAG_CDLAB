# Assistant pédagogique RAG — cours de terminale (readme fait avec IA pour info.)

Prototype réalisé dans un notebook Kaggle : il découpe des cours en passages, calcule leurs embeddings avec `Qwen/Qwen3-Embedding-0.6B`, retrouve les passages pertinents pour une question, puis génère une réponse avec un modèle servi par Groq (`openai/gpt-oss-120b`).

## Contenu

- [`fadhili-akram-rag-valu.ipynb`](fadhili-akram-rag-valu.ipynb) : notebook Kaggle, avec ses sorties d'exécution.
- [Vidéo de démonstration](demo-rag-llm-api.mp4) : version compressée de la démonstration fournie.

## Exécuter dans Kaggle

1. Importer le notebook dans Kaggle et joindre le dataset de cours qui fournit `dataset_cours_nettoye.csv`. Le notebook attend le fichier à l'emplacement `/kaggle/input/datasets/grandiosfotisemo/dataset-cours-terminale/dataset_cours_nettoye.csv`, avec les colonnes `cours` et `titre_chapitre`. Adapter ce chemin à l'emplacement réel si besoin.
2. Activer un GPU pour la cellule qui charge le modèle sur `cuda` et autoriser l'accès Internet au téléchargement initial du modèle et aux appels Groq. Les paramètres exportés dans le notebook ne garantissent pas ces options lors d'une nouvelle importation.
3. Dans les secrets du notebook Kaggle, créer `GROQ_API_KEY` avec une clé Groq personnelle. Aucune clé n'est incluse dans ce dépôt.
4. Exécuter les cellules dans l'ordre. La cellule d'installation ajoute le paquet `groq`; `torch`, `sentence-transformers`, `transformers`, `numpy` et `pandas` doivent être disponibles dans l'environnement.

Le notebook est publié comme démonstrateur et nécessite le dataset et une clé API pour reproduire ses résultats. Les appels au modèle distant peuvent entraîner des coûts ou être soumis à des limites selon le compte utilisé.
