# Atelier Aquarelle — site Rickart

Site statique (une seule page HTML) pour :
- présenter les ateliers d'aquarelle (Biot, Antibes, Juan-les-Pins) ;
- montrer des œuvres et des cartes de Noël peintes à la main ;
- vendre des cartes de Noël et des bons cadeaux via des liens de paiement Stripe.

## Mettre en ligne (GitHub Pages)

1. Créer un dépôt GitHub vide (par exemple `atelier-aquarelle-site`).
2. Pousser ce dossier :
   ```bash
   git remote add origin https://github.com/<votre-compte>/atelier-aquarelle-site.git
   git push -u origin main
   ```
3. Dans le dépôt : **Settings → Pages → Build and deployment → Deploy from a branch → `main` / `(root)`**.
4. Le site sera disponible à `https://<votre-compte>.github.io/atelier-aquarelle-site/`.

## Activer les paiements (Stripe Payment Links)

1. Créer un compte Stripe avec le SIRET de l'entreprise.
2. Pour chaque produit (chaque atelier, chaque carte, chaque bon cadeau), créer un **Payment Link** dans le tableau de bord Stripe.
   - Pour les cartes, activer la collecte de l'adresse de livraison.
3. Copier chaque lien (`https://buy.stripe.com/...`) dans l'objet `LIENS` du fichier `index.html`, en remplaçant la valeur `REMPLACER-...` correspondante.
4. Les boutons restent désactivés (« Bientôt disponible ») tant qu'un lien n'est pas renseigné.

## Modifier le contenu

- Prix des cartes : remplacer `Prix à définir` (`data-prix="..."`) dans la section « Cartes de Noël ».
- Dates et ateliers : section « Ateliers ». Les dates passées doivent être retirées.
- Ajouter une œuvre : copier une `<figure>` dans la section « Œuvres » et placer l'image dans `assets/`.
