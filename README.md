# CNN Cats vs Dogs — From Scratch vs Transfer Learning

## Objectif
Comparer un modèle CNN entraîné from scratch et un modèle basé sur le transfert learning (ResNet18) sur une tâche de classification Cats vs Dogs.

## Contenu du rendu
- `notebook.ipynb` : notebook principal d’entraînement et d’évaluation.
- `train_cats_dogs.py` : script d’entraînement autonome.
- `train_cats_dogs_colab.ipynb` : notebook Colab prêt à l’emploi.
- `requirements.txt` : dépendances Python.
- `.gitignore` : fichiers et dossiers ignorés.

## Installation
```bash
cd cnn-catsdogs-BaniganteKpapou
python -m pip install -r requirements.txt
```

## Organisation des données
Le code attend un dossier `data/cats_vs_dogs/` à l’intérieur de `cnn-catsdogs-BaniganteKpapou/`.

Structure recommandée :

```
cnn-catsdogs-BaniganteKpapou/data/cats_vs_dogs/train/cat/
cnn-catsdogs-BaniganteKpapou/data/cats_vs_dogs/train/dog/
cnn-catsdogs-BaniganteKpapou/data/cats_vs_dogs/test/cat/
cnn-catsdogs-BaniganteKpapou/data/cats_vs_dogs/test/dog/
```

### En local
Placez vos images dans :

- `cnn-catsdogs-BaniganteKpapou/data/cats_vs_dogs/train/cat/`
- `cnn-catsdogs-BaniganteKpapou/data/cats_vs_dogs/train/dog/`
- `cnn-catsdogs-BaniganteKpapou/data/cats_vs_dogs/test/cat/`
- `cnn-catsdogs-BaniganteKpapou/data/cats_vs_dogs/test/dog/`

Le notebook et le script partent de ce dossier pour charger les images.

### Sur Google Colab
Copiez ou montez le dossier de données dans l’un des chemins suivants :

- `/content/data/cats_vs_dogs/`
- `/content/drive/MyDrive/<votre_chemin>/cats_vs_dogs/`

Puis exécutez le notebook Colab ou lancez le script avec :

```bash
python train_cats_dogs.py --data-dir /content/data/cats_vs_dogs
```

## Exécution
### Notebook local
```bash
cd cnn-catsdogs-BaniganteKpapou
jupyter notebook notebook.ipynb
```

### Script Python local
```bash
cd cnn-catsdogs-BaniganteKpapou
python train_cats_dogs.py --data-dir data/cats_vs_dogs
```

### Script rapide pour debug
```bash
cd cnn-catsdogs-BaniganteKpapou
python train_cats_dogs.py --data-dir data/cats_vs_dogs --epochs 1 --max-train-batches 50 --max-valid-batches 10 --max-test-batches 10
```

### Notebook Colab
Ouvrez `train_cats_dogs_colab.ipynb` dans Colab et suivez les cellules.

## Remarques importantes
- `data/`, `checkpoints/`, `*.pth` et `__pycache__/` sont ignorés par Git.
- Ne poussez pas les données ni les checkpoints dans le dépôt.
- Si vous utilisez Colab, adaptez le chemin `DATA_SRC` dans `train_cats_dogs_colab.ipynb` pour pointer vers votre Google Drive.

## Expériences incluses
- **Expérience A** : CNN entraîné from scratch.
- **Expérience B** : Transfert learning avec ResNet18 pré-entraîné.

## Résultats attendus
- Courbes loss/accuracy pour entraînement et validation.
- Métriques de test : loss, accuracy, precision et recall.
- Matrices de confusion.
