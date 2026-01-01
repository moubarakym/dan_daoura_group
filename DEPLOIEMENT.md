# 🚀 Guide de déploiement du site DAN DAOURA GROUP

## Méthode recommandée : Déploiement via GitHub + Netlify

### Étape 1 : Créer un dépôt sur GitHub

1. Allez sur [github.com](https://github.com) et connectez-vous (ou créez un compte gratuit)
2. Cliquez sur le bouton "**+**" en haut à droite, puis "**New repository**"
3. Remplissez les informations :
   - **Repository name** : `dan-daoura-group-website`
   - **Description** : "Site vitrine officiel DAN DAOURA GROUP"
   - Laissez en **Public** (ou Private si vous préférez)
   - **Ne cochez PAS** "Initialize this repository with a README" (nous avons déjà nos fichiers)
4. Cliquez sur "**Create repository**"

### Étape 2 : Connecter votre projet local à GitHub

Après avoir créé le dépôt, GitHub vous montre des commandes. Utilisez celles-ci dans votre terminal :

```bash
cd /home/moubarak/Desktop/Groupe_daoura

# Ajoutez le dépôt distant (remplacez VOTRE-USERNAME par votre nom d'utilisateur GitHub)
git remote add origin https://github.com/VOTRE-USERNAME/dan-daoura-group-website.git

# Poussez votre code vers GitHub
git branch -M main
git push -u origin main
```

**Note** : GitHub vous demandera vos identifiants. Si vous avez l'authentification à deux facteurs, vous devrez créer un "Personal Access Token" :
- Allez dans Settings → Developer settings → Personal access tokens → Tokens (classic)
- Créez un nouveau token avec les permissions "repo"
- Utilisez ce token comme mot de passe

### Étape 3 : Déployer sur Netlify

1. **Créer un compte Netlify**
   - Allez sur [netlify.com](https://www.netlify.com)
   - Cliquez sur "**Sign up**"
   - Choisissez "**Sign up with GitHub**" (c'est le plus simple)
   - Autorisez Netlify à accéder à votre compte GitHub

2. **Importer votre site**
   - Une fois connecté, cliquez sur "**Add new site**" → "**Import an existing project**"
   - Choisissez "**Deploy with GitHub**"
   - Autorisez Netlify à accéder à vos dépôts
   - Sélectionnez le dépôt `dan-daoura-group-website`

3. **Configuration du déploiement**
   - Netlify détectera automatiquement votre fichier `netlify.toml`
   - Vérifiez les paramètres :
     - **Branch to deploy** : `main`
     - **Build command** : (laissez vide ou `echo 'Site statique'`)
     - **Publish directory** : `.` (point)
   - Cliquez sur "**Deploy site**"

4. **Attendez le déploiement**
   - Le déploiement prend généralement 30 secondes à 2 minutes
   - Vous verrez un log en temps réel
   - Une fois terminé, vous verrez "**Site is live**" 🎉

5. **Votre site est en ligne !**
   - Netlify vous donne une URL automatique du type : `https://random-name-123456.netlify.app`
   - Vous pouvez la changer en cliquant sur "**Site settings**" → "**Change site name**"
   - Par exemple : `https://dan-daoura-group.netlify.app`

### Étape 4 : (Optionnel) Ajouter un nom de domaine personnalisé

Si vous avez un nom de domaine (comme `dandaouragroup.com`) :

1. Dans Netlify, allez dans "**Domain settings**"
2. Cliquez sur "**Add custom domain**"
3. Entrez votre nom de domaine
4. Suivez les instructions pour configurer les DNS chez votre registrar

## Méthode alternative : Déploiement direct par Drag & Drop

Si vous ne voulez pas utiliser GitHub :

1. Allez sur [netlify.com](https://www.netlify.com) et créez un compte
2. Cliquez sur "**Add new site**" → "**Deploy manually**"
3. **Créez un fichier ZIP** de votre projet :
   ```bash
   cd /home/moubarak/Desktop
   zip -r groupe_daoura.zip Groupe_daoura -x "*.git*"
   ```
4. Glissez-déposez le fichier ZIP dans Netlify
5. Votre site sera déployé immédiatement !

**⚠️ Attention** : Avec cette méthode, vous devrez créer un nouveau ZIP et le redéployer à chaque modification.

## 📝 Mises à jour futures

Une fois connecté à GitHub, pour mettre à jour votre site :

```bash
cd /home/moubarak/Desktop/Groupe_daoura

# Faites vos modifications aux fichiers...

# Commitez et poussez
git add .
git commit -m "Description des changements"
git push

# Netlify redéploiera automatiquement en 30 secondes !
```

## 🔧 Fonctionnalités Netlify gratuites

- ✅ HTTPS automatique et gratuit
- ✅ CDN mondial (site rapide partout)
- ✅ Déploiement automatique à chaque push GitHub
- ✅ Prévisualisation des modifications avant déploiement
- ✅ Historique des déploiements (possibilité de revenir en arrière)
- ✅ Formulaires (si vous en ajoutez plus tard)

## 📱 Vérifier votre site

Une fois déployé, testez votre site sur :
- Desktop (Chrome, Firefox, Safari)
- Mobile (testez le formulaire de devis)
- Vérifiez que les images se chargent
- Testez le bouton WhatsApp

## 🆘 Besoin d'aide ?

Si vous rencontrez un problème :
1. Vérifiez les logs de déploiement sur Netlify
2. Assurez-vous que tous les fichiers sont bien dans le dépôt GitHub
3. Vérifiez que le fichier `netlify.toml` est présent

---

**Bonne chance avec votre déploiement ! 🚀**
