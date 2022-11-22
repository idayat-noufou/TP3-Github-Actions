# Automatisation de l'intégration continue de l'API

Afin de réaliser l'automatisation, nous partons d'un unique workflow dans lequel on distinguera toutes les étapes à partir d'un name avant chaque action.
Basiquement, le fichier commence par le code ci-dessous:

```yaml
jobs:
  build-and-test:
    name: Run unit tests
    runs-on: ubuntu-latest
    defaults:
      run:
        working-directory: ./api
```
*Note: les points de suspensions(...) désignent le code tapé précédement*

## 1) Automatisation des tests unitaires


Pour réaliser les tests unitaires, on rajoute **steps** en dessous de **defaults** :

```yaml
name: GitHub Actions Tests Unitaires
run-name: ${{ github.actor }} is testing out GitHub Actions 🚀
on: [push]
jobs:
  build-and-test:
    name: Run unit tests
    runs-on: ubuntu-latest
    defaults:
      run:
        working-directory: ./api
    steps:
```
à l'intérieur de **steps**, 

* on commence par cloner le repository git actuel
```yaml
...
jobs:
  steps:
    - uses: actions/checkout@v3
```

* ensuite on choisit la version de node qui doit être installée
```yaml
jobs:
  steps:
    ...
    - name: Use Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '18.x'
```
içi, la version choisit est la version 18

* on installe les dépendences
```yaml
jobs:
  steps:
    ...
    - name: install dependencies
        run: yarn install
```


## 2) Construction et partage de l'image Docker
## 3) Ajout des tests d'intégration
## 4) Mise ne cache des dépendances