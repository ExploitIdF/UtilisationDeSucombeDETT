Signalisation dynamique - Comparaison des consommations avec le DE
####################################################################
Dans le cadre du bilans des marchés, avant leur renouvellement, Jonathan Cole a demandé que l'on compare les consommations avec le détail estimatif du marché.

Dans cette page, on présente les exploitations réalisées pour répondre à cette demande. Le marché Signalisation dynamique est pris comme exemple pour faire le prototype de la procédure.


Extraction des consommations
********************************
L'application Sucombe permet d'exporter un fichier qui pour chaque numéro de prix comporte les quantités consommées, les prix unitaires et le prix total.

On appel cette table **ExportSucombe**

Comparaison avec le **Détail estimatif**
**********************************************
Dans le DCE, le DE apparait comme un fichier ODS : `4a- DE SDY V1.ods` . 
Ce fichier contient 13 onglets, le premier étant une synthèse.

Dans un notebook Python, on peut lire chaque onglet et sélectionner les lignes dont le premier champ commence par SDY.
On appelle la table ainsi constitué **DE2020**.

L'un des *code prix*, `'SDY FS 401'`, présente une erreur manifeste que l'on corrige pour permettre la liaison avec la table ExportSucombe.










