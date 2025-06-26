# 🚀 fdock_cli

[![PyPI version](https://badge.fury.io/py/fdock-cli.svg)](https://badge.fury.io/py/fdock-cli)
[![Python versions](https://img.shields.io/pypi/pyversions/fdock-cli.svg)](https://pypi.org/project/fdock-cli/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Un outil CLI puissant pour initialiser et gérer vos projets Python avec style ! 

## 🎯 Fonctionnalités

- **Initialisation rapide** de projets Python avec structure complète
- **Gestion d'environnements virtuels** simplifiée  
- **Interface interactive** avec menu coloré
- **Scripts bash intégrés** pour automatiser vos tâches
- **Publication automatique** sur PyPI via GitHub Actions

## 📦 Installation

```bash
pip install fdock_cli
```

## 🚀 Utilisation rapide

```bash
# Installation des scripts
python -m fdock_cli.install

# Redémarrez votre terminal puis :
fdock root    # Initialiser un projet
fdock hello   # Infos du projet
```

## 📁 Structure du projet

```
fdock/
├── .github/workflows/     # 🤖 GitHub Actions (tests + publication)
├── fdock_cli/            # 📦 Package Python
│   ├── fdock_cli/        # 🐍 Code source
│   ├── README.md         # 📖 Documentation PyPI
│   ├── pyproject.toml    # ⚙️ Configuration package
│   └── LICENSE           # 📄 Licence
├── GITHUB_ACTIONS.md     # 📋 Guide GitHub Actions
└── pyproject.toml        # 🔧 Configuration outils (black, isort...)
```

## 🛠️ Développement

```bash
git clone https://github.com/ton-username/fdock_cli
cd fdock_cli/fdock_cli
pip install -e .
```

## 🚀 Publication automatique

Ce projet utilise GitHub Actions pour :
- ✅ Tester sur Python 3.7-3.12 + Ubuntu/Windows/macOS
- ✅ Vérifier la qualité du code
- ✅ Publier automatiquement sur PyPI avec les tags Git

Voir [GITHUB_ACTIONS.md](GITHUB_ACTIONS.md) pour le guide complet.

## 📄 Licence

MIT License - Voir [LICENSE](fdock_cli/LICENSE)

---

**Créé avec ❤️ pour simplifier la vie des développeurs Python !** 