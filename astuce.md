Vous souhaitez utiliser la directive `csv-table` de Sphinx pour afficher des données provenant d'un fichier CSV, mais vous rencontrez des problèmes de largeur de page. Malheureusement, `csv-table` offre très peu de contrôle sur la mise en page, notamment la taille de la police. La solution la plus robuste consiste à combiner `csv-table` avec du CSS intégré via la directive `raw:: html`.

Voici une approche combinant lecture du CSV, création du tableau HTML et application de styles CSS, en incluant des améliorations pour la gestion des données et l'adaptation à la taille de l'écran :

```rst
.. raw:: html

   <style>
   .csv-table-container {
       width: 100%; /* Important pour l'adaptation à la largeur */
       overflow-x: auto; /* Ajoute un défilement horizontal si nécessaire */
   }
   .csv-table {
       width: 100%;
       border-collapse: collapse;
       font-size: 80%; /* Taille de base de la police */
       table-layout: fixed; /* Important pour la largeur des colonnes */
   }
   .csv-table th, .csv-table td {
       border: 1px solid black;
       padding: 5px;
       text-align: center;
       word-wrap: break-word; /* Gère les longs mots */
       overflow: hidden; /* Empêche le texte de dépasser */
       text-overflow: ellipsis; /* Ajoute des points de suspension si le texte est tronqué */
       max-width: 100px; /* Largeur maximale des colonnes (ajuster selon le besoin) */
   }
   @media (max-width: 600px) {
       .csv-table {
           font-size: 60%; /* Réduit la taille sur les petits écrans */
       }
       .csv-table th, .csv-table td {
        max-width: 80px; /* Réduit la largeur des colonnes sur les petits écrans */
       }
   }
   </style>

.. raw:: html

   <div class="csv-table-container">
   <table class="csv-table">
       <thead>
           <tr>
               <th>CF\Mois</th><th>1</th><th>2</th><th>3</th><th>4</th><th>5</th><th>6</th><th>7</th><th>8</th><th>9</th><th>10</th><th>11</th><th>12</th><th>Total</th>
           </tr>
       </thead>
       <tbody>
           <tr>
               <td>Donnée très longue pour tester le retour à la ligne</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td>
           </tr>
           <tr>
               <td>Autre donnée</td><td>10</td><td>20</td><td>30</td><td>40</td><td>50</td><td>60</td><td>70</td><td>80</td><td>90</td><td>100</td><td>110</td><td>120</td><td>780</td>
           </tr>
       </tbody>
   </table>
   </div>

```

**Améliorations importantes :**

*   **Conteneur avec défilement horizontal :** L'ajout d'un conteneur (`<div class="csv-table-container">`) avec `overflow-x: auto;` permet d'ajouter une barre de défilement horizontale si le tableau est trop large pour l'écran. C'est crucial pour l'adaptabilité.
*   **`table-layout: fixed;` :** Cette propriété CSS est *essentielle* pour contrôler la largeur des colonnes. Sans elle, le navigateur essaie d'ajuster la largeur des colonnes en fonction du contenu, ce qui peut causer des dépassements.
*   **`max-width` sur les cellules :** Définir une largeur maximale (`max-width`) sur les cellules (`th` et `td`) permet de limiter la largeur de chaque colonne et d'éviter que le tableau ne devienne trop large. Ajustez cette valeur selon vos besoins.
*   **`word-wrap: break-word;` et `overflow: hidden; text-overflow: ellipsis;` :** Ces propriétés permettent de gérer les longs mots en les coupant et en ajoutant des points de suspension si le texte dépasse de la cellule, améliorant ainsi la lisibilité.
*   **Media Queries (`@media`) :** L'utilisation de media queries permet d'ajuster la taille de la police et la largeur des colonnes en fonction de la taille de l'écran (ici, pour les écrans de moins de 600px de large, typiquement les téléphones portables).

**Intégration avec les données CSV :**

Pour intégrer les données de votre fichier CSV, vous devez utiliser Python et le module `csv` pour lire le fichier, puis générer le code HTML du tableau dynamiquement. Voici un exemple :

```python
import csv

def generate_html_table_from_csv(csv_filepath):
    html = """
    <div class="csv-table-container">
    <table class="csv-table">
    <thead>
        <tr>
    """
    try:
        with open(csv_filepath, 'r', encoding='utf-8') as csvfile:
            reader = csv.reader(csvfile)
            header = next(reader)
            for cell in header:
                html += f"<th>{cell}</th>"
            html += "</tr></thead><tbody>"

            for row in reader:
                html += "<tr>"
                for cell in row:
                    html += f"<td>{cell}</td>"
                html += "</tr>"
            html += "</tbody></table></div>"
        return html
    except FileNotFoundError:
        return "<p>Fichier CSV non trouvé.</p>"
    except Exception as e:
        return f"<p>Erreur lors de la lecture du CSV : {e}</p>"

# Exemple d'utilisation dans un fichier .rst :

# .. raw:: html
#
#    {{ generate_html_table_from_csv("votre_fichier.csv") }}

#Dans le fichier conf.py ajouter:
#def setup(app):
#    app.add_js_file('js/copy.js')
#    app.add_css_file('css/custom.css')
#    app.add_html_math_renderer(mathjax)
#    app.builder.templates.environment.globals.update({
#        'generate_html_table_from_csv': generate_html_table_from_csv,
#    })
```

Dans votre fichier `.rst`, vous utiliserez ensuite :

```rst
.. raw:: html

   {{ generate_html_table_from_csv("votre_fichier.csv") }}
```

**Explication :**

*   La fonction `generate_html_table_from_csv` lit le fichier CSV, génère le code HTML du tableau et le retourne sous forme de chaîne de caractères.
*   L'utilisation de `{{ ... }}` dans le fichier `.rst` permet d'insérer le résultat de l'appel de la fonction Python.

Cette approche est beaucoup plus robuste et offre un contrôle total sur l'apparence des tableaux CSV dans votre documentation Sphinx. Elle gère également les problèmes de largeur de page et offre une meilleure expérience utilisateur.
