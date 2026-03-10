# Prototype de Game Intelligence Football

Prototype de détection et de scoring des courses vers l’avant à partir de données de tracking football de type broadcast, en utilisant le dataset d’exemple de Metrica Sports.

## Vue d’ensemble du projet

Ce projet explore comment extraire et quantifier des mouvements offensifs sans ballon à partir de données spatio-temporelles de tracking football.

À partir du dataset Metrica Sports, le notebook construit une première pipeline de bout en bout pour :

- charger et parser les données brutes de tracking et d’événements
- fusionner les deux équipes dans une seule table de tracking au niveau match
- convertir les coordonnées normalisées en coordonnées métriques
- calculer les vitesses des joueurs
- détecter et nettoyer les vitesses aberrantes
- identifier des séquences de course rapide
- filtrer des courses strictement orientées vers l’avant
- ajouter un contexte à partir du log événementiel
- calculer un score contextuel simple de course
- agréger les résultats au niveau joueur

Le projet est pensé comme un premier prototype de game intelligence, inspiré de workflows d’analytics football pour le scouting et l’analyse de match.

## Données utilisées

Ce projet utilise le Metrica Sports Sample Data.

Fichiers attendus dans le dossier `data/` :

- `Sample_Game_1_RawTrackingData_Home_Team.csv`
- `Sample_Game_1_RawTrackingData_Away_Team.csv`
- `Sample_Game_1_RawEventsData.csv`

Le dataset n’est pas inclus dans ce dépôt.

## Structure du dépôt

```text
football-game-intelligence-prototype/
├── data/
├── images/
│   ├── top10_max_run_score.png
│   └── top10_forward_runs_volume.png
├── notebooks/
│   └── football_game_intelligence_prototype.ipynb
├── src/
├── README.md
├── requirements.txt
├── .gitignore
└── LICENSE
