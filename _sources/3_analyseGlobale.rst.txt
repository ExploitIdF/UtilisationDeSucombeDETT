Analyses budgétaires par type, par marché et par an
#######################################################
Sucombe enregistre les commandes, les prestations et les constats dans une base de données que l'on a pu exploiter 
(Export du 7/11/2024 qui pourrait être mis à jour en tant que de besoin).

.. toctree::
   :hidden:
   :maxdepth: 3

   31_preventif
   33_nonConstate
   34_annee23.rst
   36_bilans
   38_fournisseurs
   39_divers

Dans les montants des constats présentés ci-dessous, l'année à laquelle un constat est associé est l'année d'engagement budgétaire de la prestation.
Une partie des constats sont des payements qui interviennent les années suivantes. 
Pour l'année 2024, tout particulièrement, les montants présentés sont les valeurs connues au 7/11/2024 et non pas les valeurs définitives.

Il faut aussi savoir que les engagements totaux considérés ne tiennent pas compte des **désengagements** qui peuvent avoir lieu quand une prestation est constatée *définitivement* et assez tôt, pour un montant inférieur à l'engagement. 
En effet, les désengagements faits dans Chorus ne sont pas répercutés dans Sucombe.

On pourra ajouter le calcul des montants constatés définitivement avant le 1er novembre, si cette date permet encore d'obtenir les désengagements et de réengager les AE ainsi récupérées. A défaut de fournir les désengagements effectifs, cela permettra de mesurer avec Sucombe un potentiel.

Pour les 5 dernières années, sur 25 M€ d'engagements annuels enregistrés dans Sucombe, 8M€ n'ont pas été constatés.

Montants par axe budgétaire
*******************************
On distingue 2 grands axes : 

* AFITF (Principalement les investissements de renouvellement)
* LFI (Principalement le fonctionnement)

.. csv-table::
   :header: Année \\k€ HT,AFITF engagés,AFITF  constatés, LFI engagés,LFI  constatés
   :widths: 20, 20,20, 20,20
   :width: 80%

      2020,6546,6156,13294,12242
      2021,7392,7045,13491,12096
      2022,5434,5169,13094,12556
      2023,8105,7345,13988,12985
      2024,3618,2067,15812,10504


Montants par type de prestation
*************************************
Pour chaque prestation, on définit un type parmi la liste suivante :

* Curatif
* :doc:`Preventif<31_preventif>`
* Fourniture
* Evolutif
* Prestations intellectuelles
* Urgence

On a calculé sur la période 2020-2024 les montants moyens engagés et les montants moyens constatés, par type de prestation.

.. csv-table::
   :header: Type \\k€ HT,Montants engagés,Montants constatés
   :widths: 20, 20,20
   :width: 60%

      Curatif,7092,6241
      Evolutif,2646,2377
      Fourniture,3236,2917
      Prestations intellectuelles,1511,1054
      Preventif,5217,4620
      Urgence,169,152
      Total,19871,17361

Les qualifications selon la typologie ne sont pas uniformes, ils varient selon les marchés et les agents qui saisissent les données dans Sucombe.
Par exemple, les prestations de maintien en condition opérationnelle (MCO) des marchés d'UIRC sont parfois classés dans le type Préventif, 
mais le plus souvent, elles ne le sont pas.

La typologie ne permet pas d'identifier les prestations indispensables et celles sur lesquelles il serait possible de faire des impasses, sans atteindre la 
continuité du service. 
Une typologie complémentaire pourrait être élaborée en s'appuyant sur les **numéros de prix**. 
La base de donnée permettrait alors de calculer les montants correspondant à cette nouvelle typologie.

Montants (tous types) par Lieux
************************************
Sucombe comporte un champ **Lieu** qui prend 26 valeurs, lesquelles sont, le plus souvent, des (groupes de) tunnels.

Les dépenses liées à la gestion du trafic ou qui ne peuvent pas être affectées à un tunnel particulier sont associées aux *lieux*
PCTT, SIRIUS, SIREDO  ou encore *Tous tunnels*.


Le tableau suivant donne les valeurs moyennes des montants globaux, sur les 5 dernières années.

.. csv-table::
   :header: Lieu \\ k€ HT,Montants engagés,Montants constatés
   :widths: 20, 20,20
   :width: 60%
      
      Taverny,129,114
      Bobigny-Lumen-Norton,770,686
      La Courneuve,100,94
      Landy,666,597
      Boissy-Saint-Léger,86,62
      Champigny,405,354
      Thiais,260,196
      Nogent,833,694
      Antony,199,176
      Bicêtre,504,429
      Fresnes,91,80
      Italie,68,55
      Orly,172,137
      Ambroise PARE,305,257
      Sévines,143,122
      Saint Cloud,266,236
      Nanterre / La Défense,2094,1953
      Fontenay le Fleury,59,47
      Chennevières,83,71
      Bellerive,377,317
      Neuilly,138,123
      Tous tunnels,4596,4041
      SIRIUS et TUNNELS,40,5
      PCTT,1154,1023
      SIREDO,200,130
      SIRIUS,6124,5353
      Total,19862,17352



