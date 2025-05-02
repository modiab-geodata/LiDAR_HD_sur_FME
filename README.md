## Contexte du projet
Ce projet a été réalisé au cours de mon Master en Géomatique Appliquée aux Études Urbaines et aux Risques, dans le cadre du cours SIG et Automatisation. L’objectif était de concevoir un workflow FME automatisé sur un thème libre. Ayant travailler sur le projet LiDAR HD lors de mon alternance à l'IGN (Institut National de l'Information Géographique et Forestière), j’ai choisi de développer une chaîne de traitement permettant de générer automatiquement des modèles numériques (terrain, surface et hauteur) à partir de nuages de points LiDAR classés.

## Objectifs du projet
  - Télécharger et intégrer des nuages de points LiDAR classés depuis le portail de l’IGN.
  - Automatiser, via FME, la génération des modèles suivants 
  - MNT (Modèle Numérique de Terrain) : Représente la topographie du sol (hors végétation et bâtiments...).
  - MNS (Modèle Numérique de Surface) : Inclut tous les objets du sol et du sursol (bâtiments, végétation...).
  - MNH (Modèle Numérique de Hauteur) : Différence entre le MNS et le MNT, donnant la hauteur des objets.

## Contenu du projet
  - Le workflow FME (.fmw)
  - Lien de télechargement de deux dalles de nuages de points au format .copc.laz
  - Un MNT, MNS et MNH au format .tif
  - Image du workflow FME

## Visuualisation
- Les résultats ont été intégrés dans QGIS pour valider la qualité des modèles produits (comparaison visuelle, vérification des hauteurs, etc.).

## Prérequis
  - FME Form (Desktop)
  - QGIS (pour la visualisation)
  - Données LiDAR classées (2 dalles) au format .copc.laz

## Transformers FME utilisés

Le workflow utilise les transformers suivants pour le traitement et la génération des modèles numériques :
  - AttributeRenamer : pour renommer les attributs en sortie des traitements intermédiaires
  - PointCloudCombiner : pour fusionner mes 2 dalles de nuages de points en une seule entité
  - Reprojector : pour reprojeter les données en Lambert 93
  - PointCloudFilter : pour filtrer les points en fonction de leur classification (sol, végétation, etc.)
  - RasterDEMGenerator : pour générer des modèles numériques à partir de données LiDAR
  - NumericRasterizer : pour convertir les valeurs numériques en rasters
  - RaterHillshader : pour créer une visualisation ombrée du MNT
  - FeatureWriter : pour exporter les fichiers raster (MNT, MNS, MNH) au format .tif

## Auteur
**Moussa DIABY**  
Projet réalisé dans le cadre de mon Master avec FME.

