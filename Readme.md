Le projet Houssing  est une analyse évaluant les différents prix des maisons de la californie et pemettant de predire
le prix d'une maison avec la methode de datascientist
La data utiliser est  : "housing.csv" (disponible dans le dossier télécharger)

Pour utiliser :
- Avoir un environnement python bien établie et préparer pour la fonction du machine learning (les librairies sikit-learn, pandas,numpy ...)
- Télécharger le dossier
- Le compiler dans vôtre éditeur de choix

Ce guide pourrais mieux aider à comprendre le code

Colonnes :

1. longitude: A measure of how far west a house is; a higher value is farther west
2. latitude: A measure of how far north a house is; a higher value is farther north
3. housingMedianAge: Median age of a house within a block; a lower number is a newer building
4. totalRooms: Total number of rooms within a block
5. totalBedrooms: Total number of bedrooms within a block
6. population: Total number of people residing within a block
7. households: Total number of households, a group of people residing within a home unit, for a block
8. medianIncome: Median income for households within a block of houses (measured in tens of thousands of US Dollars)
9. medianHouseValue: Median house value for households within a block (measured in US Dollars)
10. oceanProximity: Location of the house w.r.t ocean/sea


Analyse des données :

1. Analyse de la forme
    - Target : median_house_value
    - Size : (20640, 10)
    - Features types : 
        float64 = 9 ,
        object = 1
    - Nan : très peu de variables manquantes (moins de 2% pour la seule variabe "total_bedrooms")

2. Analyse du fond
    - Analyse de la target "median_house_value" : la Valeur médiane des maisons au sein d'un groupe de maisons  
        spécifique, probablement un bloc ou un ensemble de maisons contiguës
        max_value = 500001.0 $
        min_value =  14999.0 $
        mean_value = 206855.81690891474 $
    - Analyse des features
        . les variables de types floatants ne suivent pas une loi normal 
        . ocean_proximity----- ['NEAR BAY' '<1H OCEAN' 'INLAND' 'NEAR OCEAN' 'ISLAND'] == ["PRÈS DE LA BAIE" ,"MOINS 
          D'1H DE L'OCÉAN" ,"INTÉRIEUR DES TERRES" ,"PRÈS DE L'OCÉAN" ,"ÎLE"]
          Nous pourrons peut être constituer pour cette variable un résultat binaire qui prend 0 au cas oû la maison
          est situé à "INTÉRIEUR DES TERRES" et 1 pour les autres cas
        . les variables 'totalRooms', 'totalBedrooms','population' et 'household' sont fortement colrréler entre elles
          Mon hypothèse est que ces variables liées sont très importantes à la détermination du prix d'un maison 