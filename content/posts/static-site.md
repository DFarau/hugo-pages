---
title: Les sites statiques
date: 2023-11-17
weight: 5
description: "Explication d'un site statique, ses avantages et inconvénients"
draft: false
tags: ["Documentation"]
---

## Introduction

Des performances améliorées, une sécurité accrue et une facilité d'utilisation sont autant de raisons qui rendent les générateurs de sites statiques attrayants.

L'objectif des générateurs de sites web est de transformer le contenu en fichiers HTML. La plupart d'entre eux sont des "générateurs de sites dynamiques". Cela signifie que le serveur HTTP, c'est-à-dire le programme qui envoie les fichiers au navigateur pour être visualisés, exécute le générateur pour créer un nouveau fichier HTML chaque fois qu'un utilisateur final demande une page.

Au fil du temps, les générateurs de sites dynamiques ont été programmés pour mettre en cache leurs fichiers HTML afin d'éviter des retards inutiles dans la fourniture des pages aux utilisateurs finaux. Une page mise en cache est une version statique d'une page web.

## Les avantages

- **Rapidité** : les sites statiques se démarquent par leur rapidité. Contrairement aux sites dynamiques, ils évitent les requêtes de base de données et les processus de traitement à chaque demande. Les pages HTML statiques sont directement servies par le serveur, garantissant une réponse quasi instantanée.

- **Contrôle de version pour le contenu** : dans un projet, le contrôle de version est essentiel. Les sites statiques stockent le contenu, comme les articles d'un blog, sous forme de fichiers plats dans un référentiel. Cela permet un travail collaboratif, un suivi clair des modifications, et même la possibilité pour les lecteurs de signaler des erreurs ou d'apporter des corrections.

- **Sécurité** : comparés aux plates-formes dynamiques populaires comme WordPress, les sites statiques sont souvent plus sûrs. Les risques liés aux failles de sécurité, fréquents dans les systèmes complexes, sont réduits car les sites statiques se contentent de servir des pages HTML simples, minimisant ainsi les vulnérabilités.

- **Moins de complexité avec le serveur** : l'installation et la maintenance des infrastructures pour les sites dynamiques peuvent être complexes en raison des différentes versions de logiciels, dépendances et configurations. Les sites statiques simplifient cela en générant des fichiers HTML qui peuvent être servis sur n'importe quel serveur sans nécessiter une infrastructure complexe.

- **Gestion des pics de trafic** : les sites statiques sont mieux préparés pour gérer les pics de trafic. Étant donné que les pages HTML statiques nécessitent peu de ressources serveur, ils sont plus résilients face à des augmentations soudaines du trafic par rapport aux sites dynamiques qui dépendent fortement des bases de données et du traitement intensif.

## Les inconvénients 

- **Absence de contenu en temps réel** : un site statique ne permet pas d'avoir des données en temps réel, comme des indicateurs sur les tendances récentes ou un contenu changeant dynamiquement pour chaque visiteur. C'est un compromis inhérent aux sites statiques, et il est crucial de se demander si cette limitation est compatible avec les besoins du site en termes d'actualisation constante.

- **Absence de contribution utilisateur** : ajouter du contenu généré par l'utilisateur sur un site statique, comme des commentaires, est complexe. Bien que le traitement des données directement dans les pages statiques ne soit pas possible, des solutions alternatives existent. Par exemple, des services tiers peuvent gérer les commentaires et les rediriger vers vous par e-mail.

- **Absence d'interface d'administration conviviale** : la publication sur un site statique requiert généralement des étapes manuelles, ce qui contraste avec la simplicité des plateformes dynamiques comme WordPress. Des alternatives incluent des interfaces web permettant l'édition directe des fichiers sur GitHub ou des applications mobiles facilitant l'écriture et la publication en déplacement.


