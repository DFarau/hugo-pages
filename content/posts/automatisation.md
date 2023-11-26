---
title: Automatisation du déploiement et dossier public 
date: 2023-11-15
weight: 3
description: "L'automatisation du déploiement augmente l'efficacité, réduit les erreurs, simplifie la gestion et offre ainsi un cycle de développement plus rapide et fiable"
draft: false
tags: ["Documentation", "Github-Pages"]
---

## Automatisation du déploiement

L'automatisation du déploiement avec le dossier "public" sur la branche "gh-pages" apporte une efficacité significative, une réduction des erreurs et une facilité de gestion, contribuant à un cycle de développement plus rapide et fiable

### Avantages

- **Simplicité du processus** : simplifie le processus de déploiement en évitant aux utilisateurs de se rappeler des étapes spécifiques. En automatisant, il suffit de déclencher le processus, et celui-ci s'occupe de tout, de la génération du site à son déploiement sur GitHub Pages.

- **Gain de temps** : réduit le temps nécessaire pour déployer le site. Une fois configurée, la procédure peut être déclenchée rapidement, permettant aux développeurs de se concentrer davantage sur le code et les fonctionnalités plutôt que sur le processus de déploiement.

- **Réduction des trreurs** : minimise les risques d'erreurs humaines lors du déploiement manuel. Les scripts automatisés exécutent les mêmes étapes de manière cohérente, réduisant ainsi les chances d'oublier une étape critique.

- **Intégration continue** : en automatisant le déploiement, on peut intégrer cette étape dans un pipeline d'intégration continue (CI). Chaque modification du code peut déclencher automatiquement la génération du site et son déploiement, assurant ainsi une livraison continue et rapide.

- **Évolutivité** : particulièrement bénéfique pour les projets évolutifs où les mises à jour fréquentes sont nécessaires. Elle permet une mise à jour régulière et rapide du site sans nécessiter une intervention manuelle constante.

- **Consistance** : assure la consistance du processus de déploiement. Chaque déploiement est effectué de la même manière, garantissant une expérience fiable pour les utilisateurs finaux.

- **Facilité de collaboration** : si plusieurs développeurs travaillent sur le projet, l'automatisation permet de garantir que chaque membre de l'équipe suit le même processus de déploiement. Cela facilite la collaboration en réduisant les variations dans les procédures.

- **Maintenance facilitée** : lorsque des mises à jour du site sont nécessaires, la maintenance est simplifiée grâce à l'automatisation. Les développeurs peuvent effectuer les modifications nécessaires dans le code source, déclencher le processus d'automatisation, et le site est mis à jour sans effort supplémentaire.

### Marche à suivre

1. Créer un dossier public et une branche "gh-pages"

2. pousser les fichiers statiques (dossier public) vers la branche "gh-pages" du dépôt GitHub, ce qui les rend accessibles via GitHub Pages.

3. Dans les paramètres du dépôt GitHub, configurer GitHub Pages pour utiliser la branche "gh-pages" comme source. Cela indique à GitHub Pages où trouver les fichiers statiques à afficher.


## Pourquoi créer un dossier Public ?

Le dossier public dans un projet Hugo contient les fichiers générés lors de la construction du site statique. Ce dossier contient tous les fichiers HTML, CSS, JavaScript, ainsi que d'autres ressources statiques nécessaires pour rendre le site fonctionnel.

- **Hébergement sur des plateformes d'hébergement statique** : de nombreux services d'hébergement statique, tels que GitHub Pages, Netlify, Vercel, et d'autres, peuvent directement servir le contenu statique du dossier public. En poussant uniquement ce dossier, on configurez notre site pour être déployé facilement sur ces plateformes.

- **Séparation du contenu source** : le contenu source du site Hugo (fichiers Markdown, fichiers de configuration, thèmes, etc.) est généralement stocké à la racine du repository. En poussant uniquement public, on gardez une séparation claire entre le contenu source et le contenu généré.

- **Éviter les conflits de fusion** : en séparant les fichiers source des fichiers générés, on minimise les conflits de fusion potentiels lors de l'utilisation de branches ou de pull requests. On ne fusionne que les modifications dans les fichiers source, puis on régénére le contenu statique localement avant de le pousser vers le dossier public.