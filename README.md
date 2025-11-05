# amplify-demo

Automatisation du déploiement d’une application React sur **AWS Amplify** via **GitHub Actions** avec **OIDC sécurisé**.

---

## 🎯 Objectif

Montrer comment mettre en place un pipeline **CI/CD sécurisé** pour une application React hébergée sur AWS Amplify :

- Build automatique à chaque push sur `main`  
- Déploiement automatique via Amplify CLI  
- Authentification sécurisée GitHub → AWS sans clés AWS stockées  (utilisant OIDC)
- Collaboration multi-développeurs possible

---

## ⚙️ Prérequis pour la démo

- **Compte AWS** avec accès IAM  
- **Compte GitHub** et repository du projet  
- **Node.js** v18+ et **npm** installés localement  
- Optionnel : Amplify CLI pour tests locaux
```bash
npm install -g @aws-amplify/cli

🔐 Rôle IAM pour GitHub Actions (OIDC)
1️⃣ Créer le rôle IAM

Type : Web identity

Identity provider : token.actions.githubusercontent.com

Audience : sts.amazonaws.com

Trust policy restreinte à ton repo et à la branche main

2️⃣ Permissions minimales pour Amplify (Policy)

