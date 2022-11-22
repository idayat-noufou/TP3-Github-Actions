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

## 1) Automatisation des tests unitaires

Pour réaliser les tests unitaires, on rajoute **steps** en dessous de **defaults** :

```yaml
jobs:
  build-and-test:
    name: Run unit tests
    runs-on: ubuntu-latest
    defaults:
      run:
        working-directory: ./api
    steps:

```
à l'int"



## 2) Construction et partage de l'image Docker
## 3) Ajout des tests d'intégration
## 4) Mise ne cache des dépendances