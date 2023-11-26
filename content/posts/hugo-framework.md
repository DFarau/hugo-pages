---
title: Le framework Hugo
date: 2023-11-14
weight: 1
description: "Hugo, un framework de création de sites web. Populaire en tant que générateur de sites statiques open source, Hugo offre une expérience de création web plaisante grâce à sa vitesse et sa flexibilité."
image: images/hugo-logo.png
imageAltAttribute: hugo-logo
tags: ["Hugo"]
---

## Introduction

Hugo est un framework de site web **polyvalent** qui permet de générer un site statique avec Go. Contrairement aux systèmes qui construisent dynamiquement une page à chaque demande de visiteur, Hugo construit des pages lorsque l'on crée ou met à jour le contenu. Hugo est conçu pour offrir une expérience de visualisation optimale aux utilisateurs finaux et une expérience d'écriture idéale pour les auteurs de sites web.

Les sites web construits avec Hugo sont extrêmement **rapides** et **sécurisés**. Les sites Hugo peuvent être hébergés n'importe où, y compris sur GitHub Pages, Netlify, Heroku, GoDaddy, DreamHost, GitLab Pages, Surge, Firebase, Google Cloud Storage, Amazon S3, Rackspace, Azure, CloudFront et fonctionnent bien avec les CDN. Les sites Hugo fonctionnent sans avoir besoin d'une base de données ou de dépendances à des runtimes tels que Ruby, Python ou PHP.

## Hugo, un générateur de site statique

Les fichiers HTML générés par Hugo ne sont pas créés de manière dynamique. 
Cela signifie que le contenu des pages web n'est pas généré à la demande au moment où un utilisateur visite le site. Au lieu de cela, tous les fichiers HTML sont pré-générés à l'avance. 

Hugo est donc qualifié de "générateur de site statique". ([En savoir plus sur les sites statiques](../static-site))

> Cela présente des avantages en termes de **performances**, de **sécurité** et de **facilité de mise en cache**, car les fichiers HTML ne changent pas fréquemment.

Comparé à un site web dynamique, un site basé sur un serveur HTTP peut traiter un nombre similaire de pages avec une fraction des ressources (mémoire et puissance CPU) nécessaires.

{{< youtube "CdiDYZ51a2o?si=EpT8hggio0k5OS8g" >}}

## Structure du site

La structure d'un site Hugo est cruciale pour organiser efficacement le contenu, les modèles, les thèmes, et d'autres éléments. Comprendre cette architecture facilite la personnalisation et la gestion du site. 

### 1. Arborescence de répertoires

- **archetypes** : ce répertoire contient des modèles de contenu par défaut. Lorsque vous créez un nouveau contenu, Hugo utilise ces modèles comme point de départ. Cela permet d'éviter de saisir manuellement les métadonnées à chaque fois.

- **content** : le cœur du site réside dans le répertoire content. Il abrite l'ensemble du contenu du site, y compris les articles, les pages, et tout autre élément textuel. La structure des sous-répertoires facilite l'organisation et la hiérarchie du contenu.

- **data** : Hugo prend en charge l'utilisation de fichiers de données externes. Le répertoire data est l'endroit où ces fichiers peuvent être stockés. Ces données peuvent être utilisées pour générer du contenu dynamique ou pour alimenter des modèles spécifiques.

- **layouts** : les fichiers de mise en page sont stockés ici. Ces fichiers définissent la structure et la présentation du contenu. Les modèles peuvent être spécifiques à un type de contenu (par exemple, single.html pour un article individuel) ou plus généraux.

- **static** : le répertoire static est destiné à tout le contenu statique du site, tel que les images, les fichiers CSS, les fichiers JavaScript, etc. Ce contenu est directement copié dans le répertoire de sortie lors de la génération du site.

- **themes** : les thèmes sont essentiels pour personnaliser l'apparence du site. Vous pouvez installer des thèmes tiers en les clonant dans le répertoire themes. Hugo recherche les fichiers de thème dans ce répertoire pour appliquer les styles et les mises en page au site.

- **config.toml, config.yaml ou config.json** : le fichier de configuration central du site. Il contient des paramètres tels que le titre du site, la langue, les paramètres de mise en page, et d'autres configurations essentielles. La modification de ce fichier permet de personnaliser divers aspects du site.

### 2. Configurations du site

Le fichier config.toml détient une variété de configurations clés pour le site Hugo. Certaines de ces configurations incluent :

- **Paramètres du site** : titre, description, langue, etc.

- **Paramètres de rendu** : formats de date, formats de permalien, etc.

- **Paramètres du serveur de développement** : port, rechargement automatique, etc.

- **Paramètres de taxonomie** : configuration des catégories et des balises.

- **Paramètres des menus** : définition des menus de navigation.

Modifier ce fichier permet d'adapter le site en fonction des besoins spécifiques du projet.

## Les thèmes

### 1. Installation

Les thèmes sont généralement hébergés sur des dépôts Git. 

```bash
$ clone URL-du-theme themes/nom-du-theme
```

### 2. Activation

Il faut spécifier le thème actif dans le fichier de configuration config.toml.

<a id="mon-endroit-specifique"></a>

### 3. Personnalisation

- **Fichiers de surcharge** : pour personnaliser un fichier de mise en page spécifique, il faut créer un fichier avec le même chemin relatif dans le répertoire layouts du site. Hugo priorise les fichiers du site à ceux ceux du thème.
 
- **Variables de configuration** : certains thèmes permettent la personnalisation via des variables définies dans le fichier de configuration config.toml.

- **Utilisation de shortcodes** : les shortcodes sont des fragments de code réutilisables que vous pouvez insérer dans vos contenus. Ils sont particulièrement utiles pour ajouter des fonctionnalités spécifiques sans avoir à modifier directement les modèles.

([En savoir plus sur la personnalisation](../personalization))

## Modèles et mises en page

### 1. Modèles

- **Structure des modèles** : les fichiers de modèles sont généralement stockés dans le répertoire layouts. La structure de ces fichiers dépend du type de contenu auquel ils sont associés. Par exemple, un fichier single.html est utilisé pour définir le modèle d'une page unique.

- **Balises de modèle** : les balises de modèle sont des éléments spéciaux entourés de doubles accolades {{}}. Elles sont utilisées pour incorporer du contenu dynamique, des variables, et des conditions dans le modèle.

- **Fichiers partiels** : les fichiers partiels, stockés dans le répertoire partials, sont des fragments de code réutilisables. Ils peuvent être inclus dans d'autres fichiers de modèles pour éviter la redondance du code.

- **Variables de contenu** : les variables spécifiques au contenu, telles que .Title, .Date, et .Content, permettent d'accéder aux métadonnées et au contenu du fichier source associé.

### 2. Mises en page

- **Hiérarchie des mises en page** : les fichiers de mise en page peuvent être spécifiques à un type de contenu (comme single.html pour un article unique) ou plus généraux (comme list.html pour une liste de contenu). Hugo applique ces mises en page en fonction du type de contenu.

- **Fichiers d'index** : les fichiers d'index, tels que index.html dans le répertoire racine de layouts, définissent la mise en page par défaut pour les pages principales du site.

- **Mises en page de section** : Hugo permet de définir des mises en page spécifiques pour des sections particulières du site. Par exemple, le fichier layouts/section/nom-de-section.html définira la mise en page pour toutes les pages appartenant à cette section.

### 3. Personnalisation des modèles et des mises en page

La personnalisation se fait de la même manière que pour les thèmes:

- **Fichiers de surcharge**

- **Variables de configuration**

- **Utilisation de shortcodes**

([Voir "personnalisation" d'un thème](#mon-endroit-specifique))

## Les shortcodes

### 1. Structure d'un shortcode

Un shortcode dans Hugo est généralement constitué de deux parties principales, délimitées par des balises doubles accolades {{...}} :
```go
{{ $variable := .Get "paramètre" | default "valeur par défaut" }}

<div class="classe-dynamique-{{ $variable }}">
  {{ .Inner | markdownify }}
</div>
```

- **Déclaration de variables** : la première partie du shortcode peut inclure des déclarations de variables en utilisant la syntaxe Go, permettant de récupérer des paramètres spécifiés lors de l'utilisation du shortcode. Dans l'exemple, $variable est définie en fonction du paramètre "paramètre", avec une valeur par défaut si le paramètre n'est pas spécifié.

- **Utilisation des variables** : les variables déclarées peuvent ensuite être utilisées dans le reste du shortcode. Par exemple, $variable est utilisée pour dynamiquement définir une classe dans une balise ```<div>```.

- **Contenu interne** : la section {{ .Inner | markdownify }} permet d'incorporer le contenu interne du shortcode. Ce contenu peut être traité avec des opérations de pipeline, comme markdownify pour interpréter les balises Markdown.

### 2. Utilisation

Pour utiliser un shortcode dans une page ou un article Hugo, il faut insérer le shortcode avec la syntaxe ```{{```< link param="valeur" >```}}```.

## Taxonomies

Les taxonomies sont des classifications hiérarchiques pour organiser le contenu. Il existe deux types principaux de taxonomies : les taxonomies de catégories (ou de sections) et les taxonomies de tags. Ces deux types sont souvent utilisés pour trier et filtrer le contenu.

### 1. Configuration

Pour utiliser les taxonomies, il faut les définir dans le fichier de configuration config.toml. Par exemple, pour activer une taxonomie "categorie" :

```go
[taxonomies]
  categorie = "categories"
```

### 2. Attribution au contenu

Dans le front matter de chaque contenu, il est possible d'attribuer des valeurs de taxonomie. Par exemple, dans un fichier Markdown :

```go
---
title: "Mon Article"
categories: ["Technologie", "Développement"]
tags: ["Hugo", "Web"]
---
```

### 3. Utilisation dans les modèles

Il est possible de personnaliser la manière dont les pages de taxonomie sont affichées en créant des modèles spécifiques. Les fichiers de modèle pour les pages de taxonomie sont généralement stockés dans le répertoire layouts/_default/taxonomy.

## Contenu dynamique

Hugo prend en charge la génération de contenu dynamique ([En savoir plus](../dynamic-content)) à l'aide de fichiers de données externes. Ces données peuvent être utilisées pour créer des listes de pages, des menus, ou pour alimenter des modèles spécifiques.

## Déploiement

Une fois le site prêt, la génération des fichiers statiques se fait avec la commande hugo. Les fichiers résultants se trouvent dans le répertoire public. Il est possible de les déployer sur n'importe quel service d'hébergement statique de votre choix.