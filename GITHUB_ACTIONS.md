# 🚀 Guide GitHub Actions pour fdock_cli

## 📋 Vue d'ensemble

Ce projet utilise GitHub Actions pour automatiser :
- 🧪 **Tests** sur plusieurs versions de Python et OS
- 🔍 **Contrôle qualité** du code (formatting, linting)
- 📦 **Publication automatique** sur PyPI

## 🔧 Configuration requise

### 1. Secrets GitHub à configurer

Dans ton repo GitHub, va dans **Settings > Secrets and variables > Actions** et ajoute :

```
PYPI_API_TOKEN = ton_token_pypi_ici
```

### 2. Comment obtenir ton token PyPI

1. Va sur [PyPI](https://pypi.org/)
2. Connecte-toi à ton compte
3. Va dans **Account settings > API tokens**
4. Crée un nouveau token avec le scope "Entire account" ou spécifique à `fdock_cli`
5. Copie le token (il commence par `pypi-`)

## 🎯 Workflows disponibles

### 1. 🧪 Tests (`test.yml`)

**Déclenchement :**
- Push sur `main` ou `develop`
- Pull requests vers `main`
- Manuel via GitHub UI

**Ce qu'il fait :**
- Teste sur Python 3.7 à 3.12
- Teste sur Ubuntu, Windows, macOS
- Vérifie que le package s'installe
- Vérifie que les commandes CLI fonctionnent
- Contrôle qualité du code

### 2. 🚀 Publication (`publish.yml`)

**Déclenchement :**
- Push d'un tag `v*` (ex: `v2.1.3`)
- Manuel via GitHub UI

**Ce qu'il fait :**
- Build le package
- Vérifie la qualité du package
- Publie automatiquement sur PyPI

## 🏷️ Comment publier une nouvelle version

### Méthode 1 : Via tag Git

```bash
# 1. Assure-toi que tout est commité
git add .
git commit -m "🎉 Version 2.1.4 - Nouvelles fonctionnalités"

# 2. Crée et pousse le tag
git tag v2.1.4
git push origin v2.1.4

# 3. GitHub Actions va automatiquement publier sur PyPI !
```

### Méthode 2 : Manuel via GitHub UI

1. Va sur ton repo GitHub
2. Clique sur **Actions**
3. Sélectionne **🚀 Publish fdock_cli to PyPI**
4. Clique sur **Run workflow**
5. Choisis la branche et lance !

## 📊 Monitoring des workflows

### Voir les résultats

1. Va sur **Actions** dans ton repo
2. Clique sur un workflow pour voir les détails
3. Chaque étape est détaillée avec logs

### En cas d'échec

- 🔴 **Tests échouent** : Corrige le code et recommite
- 🔴 **Publication échoue** : Vérifie ton token PyPI
- 🔴 **Build échoue** : Vérifie le `pyproject.toml`

## 🎨 Badges pour ton README

Ajoute ces badges dans ton README :

```markdown
![Tests](https://github.com/ton-username/fdock_cli/workflows/🧪%20Tests%20and%20Quality%20Checks/badge.svg)
![PyPI](https://img.shields.io/pypi/v/fdock_cli)
![Python](https://img.shields.io/pypi/pyversions/fdock_cli)
```

## 🔧 Customisation

### Modifier les versions Python testées

Dans `.github/workflows/test.yml`, modifie :
```yaml
python-version: ['3.7', '3.8', '3.9', '3.10', '3.11', '3.12']
```

### Ajouter des tests

Crée un dossier `tests/` avec tes tests Python, ils seront automatiquement exécutés !

## 🎯 Bonnes pratiques

1. **Teste localement** avant de pousser :
   ```bash
   cd fdock_cli
   python -m build
   twine check dist/*
   ```

2. **Utilise des versions sémantiques** : `v2.1.3` (major.minor.patch)

3. **Documente tes changements** dans `CHANGELOG.md`

4. **Vérifie les logs** des Actions en cas de problème

## 🚀 Résultat

Une fois configuré, chaque fois que tu pushes un tag `v*`, ton package sera automatiquement :
- ✅ Testé sur toutes les plateformes
- ✅ Vérifié pour la qualité
- ✅ Publié sur PyPI
- ✅ Disponible via `pip install fdock_cli`

**C'est magique ! 🎩✨** 