# DIAGNOSTIC

## 1. Constats

Le traitement local atteint ses limites à l'échelle 1.0 : `events.json` (685 Mo) nécessite 36,97 s et 1412 Mo de RAM. À l'échelle de 50 Go, il faudrait environ 45 min et 103 Go de RAM, ce qui dépasse les capacités d'un ordinateur classique.

## 2. Analyse

La mémoire utilisée est supérieure à la taille du fichier sur le disque, car Pandas charge les données en RAM. Les jointures augmentent également la consommation mémoire. Avec l'augmentation des volumes, une seule machine devient insuffisante.

## 3. Besoins

Une architecture distribuée comme Spark répartit les données et les calculs sur plusieurs machines. Pandas reste adapté à l'exploration et au prototypage sur de petits volumes de données.