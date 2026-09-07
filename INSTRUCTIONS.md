# Setup technique pour les TD

Les notebooks et les données sont hébergés sur ce dépôt GitHub :
**https://github.com/afaflwafi/enpc_td**

Les jeux de données sont versionnés avec **Git LFS** directement dans le dépôt
(dossier `DATA/`). Il n'y a plus de raccourci Google Drive à créer.

## Ouvrir un notebook

1. Sur la page GitHub du dépôt, ouvrir le dossier `TD/` et cliquer sur le
   notebook du jour (`TD1.ipynb`, `TD2.ipynb`, …).
2. Cliquer sur le badge **« Open in Colab »** en haut du notebook.
   Google Colab s'ouvre sur une version en lecture seule.
3. `Fichier > Enregistrer une copie dans Drive`. **Travailler sur cette copie.**

## Récupérer les données (dans le notebook)

Les premières cellules du notebook s'en chargent automatiquement. Elles :

1. clonent ce dépôt sans télécharger les fichiers LFS (`GIT_LFS_SKIP_SMUDGE=1`) ;
2. récupèrent **uniquement** le fichier nécessaire au TD via
   `git lfs pull --include="DATA/dvf_idf.csv"`.

Après exécution, les données se trouvent dans `enpc_td/DATA/` (relatif au
répertoire de travail de Colab, `/content`). La variable `DATA_PATH` en tête de
notebook pointe déjà au bon endroit — vérifiez-la si vous avez modifié
l'arborescence.

> Le fichier complet `DATA/dvf_idf.csv` fait ~340 Mo : le premier `git lfs pull`
> peut prendre une minute ou deux.

## Documentation du jeu de données

Le dossier `DOCUMENTATION/` contient la notice descriptive officielle du fichier
DVF. Merci d'en prendre connaissance avant le TD1.

## Chaque semaine

Répéter la procédure ci-dessus avec le notebook de la séance. Les notebooks des
TD suivants réutilisent le dataset propre produit en fin de TD1
(`DATA/dvf_idf_clean.csv`, également versionné en LFS).

---

# Instructions pour le projet

## Présentation du projet

Nous vous proposons de construire un outil permettant de prédire la valeur de
biens immobiliers en région Île-de-France, en utilisant des algorithmes de
Machine Learning. Nous mettons à votre disposition les jeux de données, qui
seront disponibles dans leur version propre après le premier TD.

Tout au long de cette semaine, nous allons travailler sur 4 TD différents, vous
donnant les bases pour réaliser votre projet. Les sujets sont les suivants :

- **TD1** : préparation des données et visualisation
- **TD2** : réalisation d'un modèle simple et évaluation
- **TD3** : traitement de données externes, images satellites
- **TD4** : traitement de la temporalité en machine learning

Vous pouvez utiliser le code produit durant ces TD comme base de votre solution,
mais il vous sera demandé d'apporter de nouvelles choses dans votre rendu final,
que ce soit en termes de données utilisées, de traitement des données, ou de
modélisation. Vous aurez du temps après chaque TD pour travailler en groupe sur
votre projet.

## Organisation du travail en équipe

- Partez de votre copie Colab des notebooks de TD (sauvegardée dans votre Drive).
- Pour collaborer, partagez la copie Colab avec votre équipe
  (`Partager` en haut à droite) **ou** versionnez votre projet sur un dépôt
  GitHub qui vous appartient (`Fichier > Enregistrer une copie dans GitHub`
  depuis Colab, ou `git`).
- Vous êtes libres de choisir où vous versionnez votre projet ; ce dépôt-ci sert
  uniquement à distribuer les sujets et les données.
- Pour récupérer les données dans votre propre projet, réutilisez les mêmes
  commandes `git clone` + `git lfs pull --include=...` que dans les notebooks de
  TD.

## Règles du jeu et rendu attendu

Vous avez le droit, et êtes encouragés à utiliser n'importe quel jeu de données
complémentaire, tant que ces données sont open source. L'utilisation de tout
outil de code assisté (Claude Code, Codex, Mistral vibe, etc.) est autorisée,
tant que cela reste un outil. Il vous sera demandé d'expliquer votre démarche et
vos résultats, ainsi que certaines parties de votre code. Une réponse type « je
ne sais pas, l'assistant a proposé ça » sera (très) sévèrement pénalisée.

Pour ce qui est du rendu :

- Nous attendons une présentation de quelques slides présentant votre approche,
  les solutions retenues, ainsi que la répartition des tâches au sein de votre
  équipe.
- Nous interrogerons également votre vision d'un produit final utilisant votre
  modèle de prédiction. N'hésitez pas à présenter votre vision sur ce point lors
  de la soutenance.
- Nous vous demandons de nous remettre **avant le jeudi 18h** un ou plusieurs
  notebooks utilisés pour entraîner et évaluer votre modèle. Ces notebooks
  peuvent ne pas être très propres, mais doivent être fonctionnels. Un
  versionning du projet sur un dépôt GitHub est un plus, mais non obligatoire.

Au moment de la soutenance, il vous sera demandé de lancer une prédiction de
votre solution sur un jeu de données au même format que les données clean
post-TD1, mais que votre modèle n'aura jamais vu (les données de l'année 2025),
et de lancer une évaluation des performances. Nous vous demanderons alors une
analyse critique de ces dernières.

### Points de vigilance importants

- Si vous utilisez des données externes, soyez sûrs d'avoir une stratégie pour
  ajouter ces données au jeu de test au moment de la soutenance. Votre code doit
  être robuste et modulaire.
- Ce n'est pas une compétition Kaggle. Les performances de votre modèle sont
  importantes pour s'assurer que vous extrayez bien de la valeur de la donnée,
  mais ce n'est pas ce qui compte dans l'évaluation finale. Nous jugeons avant
  tout la pertinence et la rigueur de l'approche.
- Il est bien entendu interdit et contre-productif d'aller entraîner votre
  modèle sur les données 2025 trouvables en ligne, ce sera (très) visible et ne
  vous fera gagner aucun point.

Bon courage !!
