# Repas du jour

Application de gestion des repas : stock, recettes, planning, courses.

## Mettre en ligne sur GitHub Pages

1. Créez un dépôt public sur GitHub, par exemple `repas-du-jour`.

2. Déposez les fichiers `index.html`, `.nojekyll` et `README.md` à la racine du dépôt.

3. Dans **Settings → Pages**, choisissez **Deploy from a branch**, branche `main`, dossier `/ (root)`.

4. Après une minute, l'application est disponible à l'adresse `https://<votre-pseudo>.github.io/repas-du-jour/`.

## Limites à connaître

- Les données sont enregistrées dans le navigateur de chaque appareil. Elles ne sont pas synchronisées entre l'iPhone et le Mac.

- Vider les données du navigateur efface le stock et les recettes.

- Pour une synchronisation réelle, il faudra un service de stockage (par exemple Supabase ou Firebase).

