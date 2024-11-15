Analyses budgétaires par type, par marché et par an
#######################################################
Sucombe enregistre les commandes, les prestations et les constats dans une base de données que l'on a pu exploiter (11/2024).

Dans les montants des constats présentés ci-dessous, l'année à laquelle un constat est associé est l'année d'engagement budgétaire de la prestation.
Une partie des constats sont des payements qui interviennent les années suivantes. Pour l'année 2024, tout particulièrement, les montants présentés sont les valeurs connues au 7/11/2024 et non pas les valeurs définitives.

Il faut aussi savoir que les engagements totaux considérés ne tiennent pas compte des **désengagements** qui peuvent avoir lieu quand une prestation est constatée *définitivement* et assez tôt, pour un montant inférieur à l'engagement. En effet, les désengagements ne sont pas gérés dans Sucombe.

On pourra ajouter le calcul des montants constatés définitivement avant le 1er novembre, si cette date permet encore d'obtenir les désengagements et de réengager les AE ainsi récupérées. A défaut de fournir les désengagements effectifs, cela permettra de mesurer avec Sucombe un potentiel.

Pour les 5 dernières années, sur 25 M€ d'engagements annuels enregistrés dans Sucombe, 8M€ ne sont pas constatés.

Montants par axe budgétaire
*******************************
On distingue 2 grands axes : 

* AFITF (Principalement les investissements de renouvellement)
* LFI (Principalement le fonctionnement)

.. csv-table::
   :header: Année \\k€ HT,AFITF engagés,AFITF  constatés, LFI engagés,LFI  constatés
   :widths: 20, 20,20, 20,20
   :width: 80%

      2020,12725,6156,16593,12241
      2021,10929,7045,17381,12094
      2022,9432,5169,16179,12556
      2023,12871,7379,16740,12985
      2024,2904,2067,13327,10504


Montants par type de prestation
*************************************
Pour chaque prestation, on définit un type parmi la liste suivante :

* Curatif
* Preventif
* Fourniture
* Evolutif
* Prestations intellectuelles
* Urgence

On a calculé sur la période 2020-2024 les montants moyens engagés et les montants moyens constatés, par type de prestation.

.. csv-table::
   :header: Type \\k€ HT,Montants engagés,Montants constatés
   :widths: 20, 20,20
   :width: 60%

    Curatif,8370,6317
    Preventif,5507,4723
    Fourniture,5165,2931
    Evolutif,4542,2419
    Prestations intellectuelles,1978,1057
    Urgence,234,164
    Total,25799,17613

Les qualifications selon la typologie ne sont pas uniformes et peuvent varier selon les marchés et les agents qui saisissent les données dans Sucombe.
Par exemple, les prestations de maintien en condition opérationnelle (MCO) des marchés d'UIRC sont parfois classés dans le type Préventif, 
mais le plus souvent, elles ne le sont pas.

La typologie ne permet pas d'identifier les prestations indispensables et celles sur lesquelles il serait possible de faire des impasses, sans atteindre la 
continuité du service. Une typologie complémentaire pourrait être élaborée sur les **numéros de prix**. La base de donnée permettrait alors de calculer les montants correspondant à cette nouvelle typologie.


Focus sur les préventifs
*****************************
Décomposition par année
============================

En se limitant aux prestations qualifiées dans le type *Préventif*, on constate de moins fortes variations annuelles que pour les autres types. En revanche, les écarts entre montants engagés et constatés ne concernent qu'un nombre limité de marchés.

.. csv-table::
   :header: Année \\k€ HT,Montants engagés,Montants constatés
   :widths: 20, 20,20
   :width: 60%

      2020,5376,4253
      2021,5503,4548
      2022,5579,4968
      2023,5459,4877
      2024,5621,4971
      Moyenne,5507,4723

Décomposition  par marché
============================
On a regroupé des marchés quand il s'agit du renouvellement d'un marché, sur le même périmètre.  
Dans certains cas, lorsque le renouvellement du marché a créé une période *sans marché*, des commandes du périmètre ont été passées de gré à gré. 
Les montants correspondants sont classés avec les commandes simples.

.. csv-table::
   :header: Marché \\ k€ HT,Montants engagés,Montants constatés
   :widths: 20, 20,20
   :width: 60%

      AMO Tunnel,6,6
      AutoEvacuation,80,74
      Automates,55,54
      Batiment,103,102
      Climatisation,36,34
      ComSimple,387,307
      ContRéglementaire,308,286
      Divers,35,23
      Détection,494,455
      Eclairage,442,293
      MDIRIF,80,80
      MEC,620,522
      MERASS,27,4
      MIIET,299,225
      MIISST,305,275
      MIRT-LOT-1,31,31
      Onduleur,71,62
      Pompage,327,253
      Propreté,598,577
      RAU/TSE,98,91
      SignaDyn,534,448
      Ventilation,154,147
      Vidéo,409,366
      Total,5507,4723

Décomposition  par lieu
============================
Sucombe comporte un champ **Lieu** qui prend 26 valeurs lesquelles sont, le plus souvent, des (groupes de) tunnels.

Les dépenses de gestion de trafic ou qui ne peuvent pas être affectées à un tunnel particulier sont associées aux *lieux*
PCTT, SIRIUS, SIREDO  ou encore Tous tunnels.

Le tableau suivant donne les valeurs moyennes des montants de préventifs, sur les 5 dernières années.

.. csv-table::
   :header: Lieu \\ k€ HT,Montants engagés,Montants constatés
   :widths: 20, 20,20
   :width: 60%

      Ambroise PARE,142,124
      Antony,101,89
      Bellerive,191,164
      Bicêtre,254,228
      Bobigny-Lumen-Norton,390,320
      Boissy-Saint-Léger,46,44
      Champigny,180,157
      Chennevières,53,47
      Fontenay le Fleury,30,24
      Fresnes,52,48
      Italie,18,14
      La Courneuve,48,47
      Landy,238,219
      Nanterre / La Défense,1114,1008
      Neuilly,73,67
      Nogent,420,332
      Orly,102,83
      PCTT,277,238
      SIREDO,20,1
      SIRIUS,895,687
      Saint Cloud,145,134
      Sévines,64,60
      Taverny,61,57
      Thiais,110,103
      Tous tunnels,366,315


Montants (tous types) par Lieux
************************************
Le tableau suivant donne les valeurs moyennes des montants globaux, sur les 5 dernières années.

.. csv-table::
   :header: Lieu \\ k€ HT,Montants engagés,Montants constatés
   :widths: 20, 20,20
   :width: 60%

      Ambroise PARE,330,268
      Antony,201,185
      Bellerive,362,326
      Bicêtre,502,445
      Bobigny-Lumen-Norton,817,698
      Boissy-Saint-Léger,70,65
      Champigny,468,368
      Chennevières,90,79
      Fontenay le Fleury,67,51
      Fresnes,112,86
      Italie,77,59
      La Courneuve,113,102
      Landy,723,611
      Nanterre / La Défense,2333,1972
      Neuilly,149,133
      Nogent,905,712
      Orly,181,148
      PCTT,1368,1050
      SIREDO,241,131
      SIRIUS,8863,5377
      Saint Cloud,268,246
      Sévines,142,132
      Taverny,133,122
      Thiais,260,204
      Tous tunnels,7017,4053



