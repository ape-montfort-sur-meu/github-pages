# Déploiement du site web static sur GitHub Pages

Le site web statique est généré via Sphinx dans des fichiers au format Markdown (avec [MyST parser](https://myst-parser.readthedocs.io/en/latest/)).

## Génération du site web en local

```bash
# Installation des dépendances python
python -m pip install -U -r requirements/deploy.txt
# Génération
sphinx-build -b html content content/_build/html
# optimized (quiet, multiprocessing, doctrees separated)
sphinx-build -b html -d content/_build/cache -j auto -q content content/_build/html
```

Ouvrez la page `content/_build/index.html` dans un navigateur web.

## Génération avec rendu en direct

```bash
sphinx-autobuild -b html content/ content/_build
```

Ouvre la page <http://localhost:8000> dans un navigateur web pour voir le rendu HTML mis à jour lorsque les fichiers sont sauvegardées.

---

## Deploiment du site web statique

Le site web statique est hébergé sur GitHub pages et déployé pour chaque commit poussée sur la branche main.
