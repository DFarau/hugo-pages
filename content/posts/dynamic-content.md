---
title: Le contenu dynamique
date: 2023-11-15
weight: 4
description: "Un langage de balisage léger : les bases de sa syntaxe et son utilisation dans Hugo."
draft: false
tags: ["Documentation"]
---

La gestion du contenu dynamique dans Hugo offre une flexibilité considérable pour créer des sites web riches en fonctionnalités et qui s'adaptent aux besoins des utilisateurs

## Fichiers markdown
Les fichiers Markdown constituent la base du contenu dans Hugo. Chaque page, article, ou section du site est généralement représenté par un fichier Markdown. Ces fichiers contiennent du contenu textuel, structuré à l'aide de balises Markdown:
- Titres : utilisez # pour les titres, ## pour les sous-titres, etc.
- Paragraphes : séparez les paragraphes par des lignes vides.
- Liens : [Texte du lien](URL).
- Images : ![Texte alternatif](URL de l’image).
- Listes : utilisez - ou * pour les listes à puces, et des chiffres pour les listes ordonnées.
- Gras et Italique : **gras**, *Italique*.

## Front matter
Chaque fichier Markdown peut inclure une section appelée "front matter" située entre deux lignes de trois tirets (---). Cette section est utilisée pour définir des métadonnées spécifiques à la page, telles que le titre, les tags, les catégories, etc. Les métadonnées varient en fonction du type de contenu.

Exemple de front matter :

```go
---
title: "Mon Article"
date: 2023-01-01
tags: ["Hugo", "Web"]
categories: ["Développement"]
---
```

## Pages

Dans Hugo, les pages peuvent être de différents types, tels que page, post, section, etc. Chaque type de page peut avoir son propre modèle associé, déterminant la façon dont le contenu est affiché.

## Listes et boucles

Il est possible d'utiliser des boucles pour itérer sur des pages spécifiques et afficher dynamiquement le contenu.

Exemple de boucle pour afficher une liste d'articles :

```go
{{ range where .Pages "Type" "post" }}
  <h2>{{ .Title }}</h2>
  <p>{{ .Summary }}</p>
{{ end }}
```

## Paramètres de configuration

Le fichier config.toml permet de configurer divers aspects du site, y compris des paramètres liés au contenu dynamique. On peut y définir des variables globales, spécifier des chemins, activer ou désactiver des fonctionnalités, etc.

Exemple de configuration pour activer la génération des pages en plusieurs langues :

```toml
[languages]
  [languages.en]
    contentDir = "content/en"
  [languages.fr]
    contentDir = "content/fr"
```

## Formats de contenu alternatifs

Hugo prend en charge différents formats de contenu pour une même page. Il peut y avoir une page avec du contenu Markdown, mais également fournir une version en HTML, JSON, etc. Cela permet de rendre le contenu accessible de différentes manières.

## Contenu imbriqué

Il est possible d'imbriquer du contenu les uns dans les autres pour créer des structures complexes. Par exemple, un répertoire peut contenir des sections, qui contiennent des pages, qui contiennent des sections, et ainsi de suite.

## Shortcodes

Les shortcodes sont des fragments de code réutilisables qui permettent d'ajouter des fonctionnalités spécifiques dans le contenu d'une page. Cela facilite l'insertion de contenu dynamique sans avoir à répéter du code HTML complexe.

## Génération conditionnelle

Hugo offre des fonctionnalités de génération conditionnelle qui permettent de décider d'afficher ou non certains éléments en fonction de critères spécifiques, tels que la date de publication, les tags, etc.

Exemple de génération conditionnelle basée sur les tags :

```go
{{ if in .Params.tags "important" }}
  <p>Cet article est marqué comme important.</p>
{{ end }}
```
