# 🚀 Politique de contribution - Projet Depot

Bienvenue dans le projet **Depot** !  
Ce fichier explique comment contribuer correctement au projet et suivre le workflow GitFlow.

---

## 🌳 Branches principales

| Branch | Rôle |
|--------|------|
| **main** | Branche stable et déployable à tout moment (production). |
| **develop** | Branche d’intégration pour regrouper les nouvelles features (pré-production). |

---

## 🌱 Branches secondaires

| Branch | Rôle | Source | Merge vers |
|--------|------|--------|------------|
| **feature/** | Développement d’une fonctionnalité | develop | develop |
| **release/** | Préparer une version stable avant release | develop | main + develop |
| **hotfix/** | Corriger un bug critique en production | main | main + develop |

**Exemples de nommage :**

---


## 📋 Règles de contribution (Pull Requests)

1. Créer une **issue** ou un ticket pour chaque fonctionnalité.
2. Créer une **branche feature** depuis `develop`.
3. Commits **petits et explicites** (Conventional Commits recommandés).
4. Rebase régulier sur `origin/develop` :
```bash
git fetch origin
git rebase origin/develop


#Release
#Tag sur main après merge
git checkout main
git tag vX.Y.Z
git push --tags

#Back-merge release → develop
git checkout develop
git merge --no-ff main
git push


#Hotfix
#Brancher depuis main
git checkout -b hotfix/fix-bug main
