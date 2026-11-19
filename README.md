# Dofus Kikimeter

Application Windows expérimentale destinée à reproduire **en temps réel** le journal visible de **Dofus Unity 3.x** dans une fenêtre indépendante, en conservant le texte, l'ordre et les couleurs des messages.

> **Statut : cadrage de la V1 — aucun code applicatif implémenté.**

## Objectif V1

Valider la qualité d'une capture automatique du chat de Dofus **sans sniffing réseau, injection dans le jeu, lecture mémoire ni copier-coller manuel**.

- Sélectionner à la souris une zone de l'écran (multi-écrans).
- Démarrer et arrêter explicitement un **recording**.
- Reconnaître les nouvelles lignes via capture d'écran et OCR, malgré le défilement.
- Reproduire les couleurs détectées pour chaque ligne (et, si nécessaire, chaque segment).
- Afficher le journal dans Kikimeter et sauvegarder les sessions en **TXT** et **JSONL**.
- Mesurer les erreurs de lecture, doublons, pertes possibles et latence.
- Proposer des **mises à jour automatiques ou manuelles** via des releases GitHub signées, en s'inspirant du système de [Map Traveler](https://github.com/Kahinh/map_traveller).

**Limite :** une capture visuelle ne garantit pas la récupération des lignes qui défilent avant d'avoir pu être observées. La V1 vise à mesurer cette limite et à signaler les incertitudes.

## Interface prévue

`Sélectionner une zone` · `Démarrer REC` · `Arrêter REC` · `Effacer l'affichage` · `Exporter` · `Paramètres / Mises à jour`

## Pistes techniques (à valider)

- **Windows 10/11**, application desktop **Tauri 2 + Rust**.
- **Windows Graphics Capture** pour l'acquisition de la zone.
- Détection des lignes et du défilement avec OpenCV ou équivalent.
- Benchmark **Windows OCR / PaddleOCR / Tesseract** avant sélection définitive.
- Pipeline asynchrone de capture, reconnaissance, déduplication, affichage et export.
- **Tauri Updater** et GitHub Releases, à adapter après inspection de Map Traveler.

## Périmètre

La V1 ne calcule **pas** les dégâts, le DPS, les statistiques de joueurs ou les éléments des sorts. Ces fonctionnalités sont envisagées pour une version ultérieure.

## Suivi

Voir [Issue #1 — Cahier des charges V1](https://github.com/Kahinh/dofus-kikimeter/issues/1) pour les exigences détaillées et les critères de validation.

## Développement

Aucune application n'est encore distribuée. Ce dépôt contient pour le moment uniquement la documentation et la préparation du projet.
