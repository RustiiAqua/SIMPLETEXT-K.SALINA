# CLEF 2024 SimpleText : Tâches

[Domicile](./) | [Appel à communications](./CFP) | [Dates importantes](./dates) | [Tâches](./tasks) | [Outils](./tools) | [Programme](./program) | [Publications](./publications) | [Organisateurs](./organizers) | [Contact](./contact) | [Référence CLEF-2023](https://simpletext-project.com/2023/clef/)

---
## Comment participer
Pour participer, vous devez vous inscrire au [CLÉ](https://clef2024.clef-initiative.eu/index.php) site internet: [http://clef2024-labs-registration.dei.unipd.it/](http://clef2023-labs-registration.dei.unipd.it/). 

Tous les membres de l’équipe doivent s’inscrire à la liste de diffusion de SimpleText : [https://groups.google.com/g/simpletext](https://groups.google.com/g/simpletext). 

Les données seront mises à la disposition de tous les participants inscrits.

## Tâche 1 : Récupération de passages à inclure dans un résumé simplifié

Dans le cadre d’un article de vulgarisation scientifique destiné au grand public, cette tâche vise à récupérer des passages, qui peuvent aider à la compréhension de cet article, à partir d’un large corpus de résumés académiques et de métadonnées bibliographiques. Les passages pertinents doivent se rapporter à l’un des sujets de l’article source. Ces passages peuvent être complexes et nécessiter une simplification supplémentaire pour être effectués dans les tâches 2 et 3. La tâche 1 se concentre sur la récupération de contenu.

### Data
Nous utilisons les articles de vulgarisation scientifique comme source pour les types de sujets qui intéressent le grand public et comme validation du niveau de lecture qui lui convient. Le corpus principal est un large ensemble de résumés scientifiques et de métadonnées associées couvrant le domaine de l’informatique et de l’ingénierie. Nous réutilisons la collection de résumés académiques de l’ensemble de données du Citation Network ([12e version sortie en 2020](https://www.aminer.cn/citation)). Cette collection a été extraite de DBLP, ACM, MAG (Microsoft Academic Graph) et d’autres sources. Les demandes de recherche sont basées sur des articles de presse populaire destinés à un public général, sur la base de _Le Gardien_ et _Tech Xplore_. Chacun de ces articles de vulgarisation scientifique représente un sujet général qui doit être analysé pour récupérer des informations scientifiques pertinentes du corpus. Nous fournissons les URL des articles originaux, le titre et le contenu textuel de chaque article de vulgarisation scientifique en tant que sujet général. Chaque sujet général a également été enrichi d’une ou plusieurs requêtes de mots-clés spécifiques extraites manuellement de leur contenu, créant ainsi une tâche familière de recherche d’informations classant les passages ou les résumés en réponse à une requête.

### Évaluation
La pertinence thématique a été évaluée l’année dernière avec un score de 0-2 sur le degré de pertinence par rapport au contenu de l’article original. En 2023, nous avons fourni une première analyse de la complexité du texte (basée sur des mesures de lisibilité) et de l’autorité (basée sur des mesures d’impact académique). En 2024, nous prévoyons de fournir des mesures d’évaluation supplémentaires sur la pertinence thématique et la complexité/crédibilité. Bien que ces critères puissent fournir différents niveaux de comparaison entre les systèmes, nous continuerons à fournir des scores de classement standard basés sur le NDCG.

## Tâche 2 : Identifier et expliquer des concepts difficiles

L’objectif de cette tâche est de décider quels concepts dans les résumés scientifiques nécessitent une explication et une contextualisation afin d’aider un lecteur à comprendre le texte scientifique. La tâche comporte deux étapes : 

i) Récupérer jusqu’à 5 termes difficiles dans un passage donné d’un résumé scientifique ii) Fournir une définition ou une explication ou les deux de ces termes difficiles.

Le corpus de la tâche 2 est basé sur les phrases des résumés de haut rang répondant aux demandes de la tâche 1.

### Évaluation
Nous évaluerons le repérage de concepts complexes en termes de complexité et de portée du concept détecté. Nous évaluerons automatiquement les explications fournies en les comparant à des références (par exemple, ROUGE, similarité cosinus, etc.). De plus, nous évaluerons manuellement les explications fournies en fonction de leur utilité par rapport à une requête ainsi que de leur complexité pour un public général. Notez que les explications fournies peuvent prendre différentes formes, par exemple le déchiffrage d’abréviations, des exemples, des cas d’utilisation, etc.

## Tâche 3 : Simplifier le texte scientifique

L’objectif de cette tâche est de fournir une version simplifiée de phrases extraites de résumés scientifiques. Les participants recevront des articles et des requêtes de vulgarisation scientifique ainsi que des résumés correspondants d’articles scientifiques, divisés en phrases individuelles.

### Data
3 utilise le même corpus basé sur les phrases des résumés de haut rang aux demandes de la tâche 1. Nos données d’entraînement sont un véritable corpus parallèle de phrases directement simplifiées provenant de résumés scientifiques du DBLP Citation Network Dataset for _Informatique_ et des articles de Google Scholar et PubMed sur _Santé et médecine_. En 2024, nous élargirons les données de formation et d’évaluation. En plus de la simplification du texte au niveau de la phrase, nous fournirons des simplifications de saisie et de référence au niveau du passage.

### Évaluation
Nous mettrons l’accent sur les mesures d’évaluation automatique à grande échelle (SARI, ROUGE, compression, lisibilité) qui fournissent une collection de tests réutilisable. Cette évaluation automatique sera complétée par une évaluation humaine détaillée d’autres aspects, essentiels pour une analyse plus approfondie. Nous évaluons la complexité des simplifications fournies en termes de vocabulaire et de syntaxe ainsi que les erreurs (syntaxe incorrecte ; anaphore non résolue due à la simplification ; répétition/itération inutile ; fautes d’orthographe, de typographie ou de ponctuation). Lors des essais précédents, presque tous les participants ont utilisé des modèles génératifs pour simplifier le texte, mais les mesures d’évaluation existantes sont aveugles aux hallucinations potentielles avec un contenu supplémentaire ou déformé. En 2024, nous fournirons de nouvelles mesures d’évaluation qui détectent et quantifient les hallucinations dans la production.

## Tâche 4 : Suivi de l’état de l’art dans les publications savantes
Dans le domaine de l’intelligence artificielle (IA), un objectif de recherche commun est le développement de nouveaux modèles capables de rendre compte des performances de pointe (SOTA). Le reporting comprend généralement quatre éléments intégraux : Tâche, ensemble de données, métrique et score. Ces tuples (Tâche, Ensemble de données, Métrique, Score) provenant de divers articles de recherche sur l’IA alimentent les classements de la communauté. Les classements, semblables aux tableaux de bord, traditionnellement organisés par la communauté, sont des plateformes affichant divers scores de modèles d’IA pour des tâches, des ensembles de données et des mesures spécifiques. Parmi les exemples de telles plateformes, citons la fonctionnalité benchmarks sur l’Open Research Knowledge Graph and Papers with Code (PwC). L’utilisation de techniques d’exploration de texte permet de passer de la sélection conventionnelle de classements basée sur la communauté à une approche automatisée d’exploration de texte. Par conséquent, l’objectif de la tâche 4 est de développer des systèmes qui, compte tenu du texte intégral d’un article sur l’IA, sont capables de reconnaître si un article sur l’IA entrant rapporte effectivement les scores du modèle sur des ensembles de données de référence, et si c’est le cas, d’extraire tous les tuples pertinents (tâche, ensemble de données, métrique, score) présentés dans l’article. 

Veuillez consulter le [Site web de la tâche 4](https://sites.google.com/view/simpletext-sota/home) Pour plus d’informations sur l’inscription, la façon de participer, la chronologie des tâches et les liens de téléchargement des ensembles de données.
### Data
Les ensembles de données d’entraînement et de test pour cette tâche sont dérivés des annotations organisées par la communauté (T, D, M, S) pour des milliers d’articles sur l’IA disponibles sur PwC (CC BY-SA). Ces articles, provenant à l’origine d’arXiv sous licences CC-BY, sont disponibles au format TEI XML, chacun accompagné d’une ou plusieurs annotations (T, D, M, S) de PwC. L’ensemble de test inclura stratégiquement uniquement les articles avec des TDM vus dans l’ensemble d’entraînement, créant ainsi un paramètre d’évaluation en quelques coups. En plus de l’évaluation en quelques coups, nous avons l’intention d’introduire un deuxième paramètre d’évaluation pour la tâche 4, évaluant les modèles dans un contexte de tir zéro, pour lequel un nouvel ensemble de données de test sera créé. Cet ensemble de données sera enrichi d’articles qui ne rapportent pas de classements afin d’entraîner les systèmes des participants à attribuer également des étiquettes correctes aux articles d’autres domaines.

### Évaluation
Les systèmes des participants seront évalués dans deux contextes d’évaluation :

Pour __Peu de coups__ évaluation, les systèmes entraînés devront prédire (T, D, M, S) des annotations sur le texte intégral d’une nouvelle collection d’articles. Les étiquettes de l’ensemble de données Gold n’incluront que les (T, D, M, S) observées au moins une fois lors de l’entraînement. Pour __Tir zéro__ évaluation, la tâche est comme ci-dessus avec une collection différente d’articles, qui ont (T, D, M, S) avec T, D ou M invisibles dans l’ensemble d’apprentissage.

Dans les deux cas, les mesures standard de rappel, de précision et de score F seront utilisées pour signaler les scores aux systèmes des participants.
