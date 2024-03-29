# ESCAPE.

Ce projet est une démonstration d'intégration de Svelte, un framework JavaScript pour la construction d'interfaces utilisateur réactives, avec Three.js, une bibliothèque JavaScript pour créer et afficher des modèles 3D dans un navigateur web.

## Description

ESCAPE. est un projet universitaire où le but est de concevoir une carte interactive pour promouvoir un objet emblématique de la région séléctionnée. Une zone cliquable sur une carte permettra à l'utilisateur de faire apparaître le ou les objets modélisés en 3D. Nous avons ici décidé de parler des Vikings et de leur célèbre Langskip ("drakkar").

Ce projet combine les fonctionnalités de Svelte et Three.js pour créer une application web interactive qui affiche un modèle 3D dans le navigateur. Le modèle 3D est chargé à partir d'un fichier GLB (format de fichier 3D) et est rendu dans une scène 3D utilisant les fonctionnalités de Three.js. L'interface utilisateur réactive est construite avec Svelte, ce qui permet une manipulation facile des états et des composants de l'application.

⚠️ Veuillez noter que le modèle 3D peut prendre un certain temps à s'afficher dans la scène 3D en fonction de la taille du fichier GLB et de la vitesse de votre connexion Internet. Cela est dû au processus de chargement et de rendu du modèle 3D dans la scène, ainsi qu'à la complexité du modèle lui-même. ⚠️

## Fonctionnalités

*   Carte intéractive avec une zone cliquable
*   Chargement et rendu de modèles 3D à l'aide de Three.js
*   Interface utilisateur réactive construite avec Svelte
*   Format responsive : l'application fonctionne sur desktop et mobile

## Installation

1. Clonez ce dépôt sur votre machine.
2. Assurez-vous d'avoir Node.js installé sur votre machine.
3. Installez les dépendances en exécutant la commande suivante dans le repertoire du projet :

```bash
npm install
```

4. Démarrez l'application en exécutant la commande suivante :

```bash
npm run dev
```

5. Ouvrez votre navigateur et accédez à l'URL http://localhost:5173.

## Site en ligne

Le site est actuellement disponible [ici](https://escape-sae.netlify.app/) !
