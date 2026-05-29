# Installation de l’application FormaSo sur Netlify

## Contenu du dossier

Le dossier contient :

- `index.html` : l’application visible par les utilisateurs
- `netlify.toml` : la configuration Netlify
- `netlify/functions/claude.js` : la fonction serverless qui appelle Claude sans exposer la clé API

## Étape 1 — Déposer les fichiers sur GitHub

1. Ouvrir le dépôt GitHub `generateur-prompt-formaso`.
2. Supprimer l’ancien fichier si besoin.
3. Cliquer sur **Ajouter un fichier** puis **Télécharger des fichiers**.
4. Déposer tout le contenu du dossier :
   - `index.html`
   - `netlify.toml`
   - le dossier `netlify`
5. Cliquer sur **Commit changes**.

## Étape 2 — Connecter le dépôt à Netlify

1. Aller sur Netlify.
2. Cliquer sur **Add new site**.
3. Choisir **Import an existing project**.
4. Sélectionner GitHub.
5. Choisir le dépôt `generateur-prompt-formaso`.
6. Paramètres :
   - Build command : laisser vide
   - Publish directory : `.`
7. Cliquer sur **Deploy site**.

## Étape 3 — Ajouter la clé Claude

Dans Netlify :

1. Ouvrir le site.
2. Aller dans **Site configuration**.
3. Aller dans **Environment variables**.
4. Ajouter une variable :

Nom :

```text
ANTHROPIC_API_KEY
```

Valeur :

```text
votre clé API Anthropic / Claude
```

5. Enregistrer.

## Étape 4 — Redéployer

1. Aller dans **Deploys**.
2. Cliquer sur **Trigger deploy**.
3. Cliquer sur **Deploy site**.

## Test

Ouvrir l’URL Netlify, remplir les champs, puis tester :

- Copier le prompt
- Améliorer mon prompt
- Générer avec Claude

Si Claude ne répond pas, vérifier en priorité :

- que la variable `ANTHROPIC_API_KEY` existe bien ;
- que le nom est écrit exactement comme indiqué ;
- que le site a bien été redéployé après l’ajout de la clé.
