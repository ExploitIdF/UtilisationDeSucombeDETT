Puisque vos fichiers sont sur **GitHub**, vous pouvez automatiser la création du PDF à chaque fois que vous mettez à jour votre documentation grâce aux **GitHub Actions**.

C'est la méthode "zéro effort" sur le long terme : vous poussez votre code, et GitHub génère le PDF pour vous.

---

## La solution : Utiliser une GitHub Action

Voici comment configurer un flux de travail (workflow) pour générer votre PDF automatiquement.

### 1. Créer le fichier de configuration

Dans votre dépôt GitHub, créez le dossier et le fichier suivants :
`.github/workflows/make_pdf.yml`

### 2. Copier ce code dans le fichier

Voici un script prêt à l'emploi qui utilise une image Docker contenant tout le nécessaire (Sphinx + LaTeX) :

```yaml
name: Build Sphinx PDF

on:
  push:
    branches: [ main ] # Se déclenche à chaque push sur la branche main

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Build PDF via Sphinx
        uses: ammaraskar/sphinx-action@master
        with:
          # On demande explicitement la sortie PDF
          build-command: "make latexpdf"

      - name: Upload PDF Artifact
        uses: actions/upload-artifact@v4
        with:
          name: Documentation-PDF
          path: _build/latex/*.pdf

```

---

## Comment ça marche concrètement ?

1. **Le déclencheur :** Dès que vous faites un `git push` sur votre branche principale.
2. **L'environnement :** GitHub démarre un serveur virtuel sous Linux.
3. **La compilation :** Il installe les dépendances et lance la commande `make latexpdf`.
4. **Le résultat :** Une fois terminé, allez dans l'onglet **"Actions"** de votre dépôt GitHub. Cliquez sur le dernier "run" réussi, et tout en bas de la page, vous trouverez un lien pour télécharger votre **PDF (Artifact)**.

---

## Pourquoi c'est idéal pour votre usage avec RESANA ?

* **Toujours à jour :** Vous n'avez plus besoin d'installer LaTeX ou Python sur votre propre ordinateur.
* **Centralisation :** Votre documentation "source" reste sur GitHub, et vous n'avez qu'à récupérer le PDF final pour le déposer sur RESANA.
* **Qualité constante :** Le PDF est généré dans un environnement propre, évitant les problèmes de polices de caractères ou d'extensions manquantes sur votre PC.

### Petite astuce "Pro" :

Si vous voulez aller encore plus loin, on peut configurer l'action pour qu'elle crée une **"Release"** GitHub automatique avec le PDF. Ainsi, vous aurez une URL fixe et permanente vers la dernière version du PDF que vous pourrez copier-coller directement dans un lien sur RESANA.

Souhaitez-vous que je vous aide à modifier le script pour **créer automatiquement une Release** avec le PDF ?
