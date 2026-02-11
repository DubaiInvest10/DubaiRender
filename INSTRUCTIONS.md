# Guide Déploiement Render

Ce dossier contient tout ce dont vous avez besoin pour mettre en ligne votre application sur Render.

## 1. Création de la Base de Données
1. Connectez-vous à [Render](https://dashboard.render.com).
2. Cliquez sur **New +** puis **PostgreSQL**.
3. Donnez un nom à votre base (ex: `dubai-invest-db`).
4. Choisissez la région la plus proche de vous.
5. Une fois créée, copiez l' **Internal Database URL**.

## 2. Création du Web Service
1. Cliquez sur **New +** puis **Web Service**.
2. Connectez votre compte GitHub et sélectionnez ce dépôt.
3. Configurez les paramètres suivants :
   - **Name** : `dubai-invest`
   - **Environment** : `Node`
   - **Build Command** : `npm install && npm run server:build`
   - **Start Command** : `npm run server:prod`

## 3. Variables d'Environnement
Dans l'onglet **Environment** de votre Web Service sur Render, ajoutez :
- `DATABASE_URL` : (Collez votre Internal Database URL)
- `NODE_ENV` : `production`

## 4. Liaison avec l'Application Mobile (APK)
Une fois que Render vous a donné votre URL (ex: `https://votre-app.onrender.com`) :
1. Ouvrez le fichier `lib/query-client.ts` dans Replit.
2. Modifiez la fonction `getApiUrl` pour retourner votre URL Render.
3. Enregistrez et générez votre APK avec Expo EAS.

---
Besoin d'aide ? Je suis là pour vous accompagner à chaque étape.
