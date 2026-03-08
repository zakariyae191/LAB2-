# Lab2 Android Security : Rooting et Analyse de Sécurité Android

## Introduction

Ce laboratoire a pour objectif de comprendre les mécanismes de sécurité du système Android et d’observer l’impact du rooting sur l’intégrité et la protection du système. Les expériences sont réalisées dans un environnement contrôlé à l’aide d’un Android Virtual Device (AVD) afin d’éviter toute modification sur un appareil personnel. Le travail consiste à configurer un émulateur Android, installer une application de test, analyser les mécanismes de sécurité d’Android, étudier Android Verified Boot, identifier les risques liés au rooting et proposer des mesures défensives.

---

## Étape 1 : Rooter l’AVD

La première étape consiste à obtenir des privilèges élevés dans l’environnement Android virtuel. Le rooting permet d’accéder à des parties du système normalement protégées. Cela permet d’observer comment les mécanismes de sécurité réagissent lorsque l’intégrité du système est modifiée.

Dans le laboratoire, l’émulateur Android est démarré avec une option permettant d’écrire dans la partition système. Ensuite, le serveur ADB est redémarré avec les privilèges root et la partition système est montée en mode lecture/écriture.

Une fois ces actions réalisées, il est nécessaire de vérifier que les privilèges root sont actifs. Cela peut être confirmé en exécutant une commande permettant d’afficher l’identité de l’utilisateur système. Si l’identifiant affiché correspond à l’utilisateur root, cela signifie que l’environnement est correctement rooté.

Cette étape permet de comprendre que le rooting donne un accès complet au système et peut potentiellement contourner certaines protections de sécurité.

---

## Étape 2 : Fiche périmètre

Avant de commencer les tests, il est nécessaire de définir clairement le périmètre du laboratoire. Cette fiche permet de préciser les conditions dans lesquelles les tests sont réalisés.

Elle doit contenir les informations suivantes :
- le nom de l’application testée et sa version
- le type d’environnement utilisé (émulateur Android ou appareil de laboratoire)
- l’objectif du test qui est de comprendre le fonctionnement du rooting et ses impacts
- la nature des données utilisées qui sont fictives
- le type de réseau utilisé pour les tests

Cette étape permet de cadrer l’analyse et d’éviter toute confusion concernant l’environnement ou les conditions d’expérimentation.

---

## Étape 3 : Démarrer un AVD propre

Afin de garantir la fiabilité des résultats, il est important de travailler sur un environnement Android propre. Cela signifie que l’émulateur doit être récemment créé ou réinitialisé.

Dans Android Studio, l’émulateur peut être lancé depuis le gestionnaire d’appareils virtuels. Il est recommandé d’utiliser une version récente d’Android afin d’observer les mécanismes de sécurité modernes.

Une vérification peut ensuite être réalisée afin de confirmer que l’émulateur est bien détecté par l’outil ADB. Cette étape garantit que l’environnement est prêt pour les manipulations suivantes.

---

## Étape 4 : Installer et lancer l’application de test

Une fois l’émulateur fonctionnel, une application de test est installée sur l’AVD. Cette application sert de support pour observer le comportement du système Android lors de différentes actions.

Après l’installation, l’application est lancée afin de vérifier qu’elle fonctionne correctement. Il est également important de noter la version de l’application utilisée dans le rapport.

Cette étape permet de préparer les scénarios de test qui seront réalisés par la suite.

---

## Étape 5 : Définir trois scénarios simples

Pour analyser le comportement de l’application, plusieurs scénarios d’utilisation doivent être définis. Ces scénarios représentent des parcours utilisateurs simples permettant de tester les fonctionnalités principales.

Exemples de scénarios :
- ouvrir l’écran d’accueil de l’application
- rechercher un élément dans l’application
- ouvrir une page de détail ou un profil

Chaque scénario doit être documenté afin de pouvoir être reproduit facilement. Il est recommandé de décrire précisément les actions réalisées par l’utilisateur.

---

## Étape 6 : Comprendre la sécurité Android

Le système Android repose sur plusieurs mécanismes de sécurité qui protègent les applications et les données.

Le premier mécanisme est le sandboxing. Chaque application fonctionne dans son propre environnement isolé, ce qui empêche une application d’accéder directement aux données d’une autre application.

Le second mécanisme est le modèle de permissions. Les applications doivent demander l’autorisation avant d’accéder à des ressources sensibles comme la caméra, le microphone ou le stockage.

Enfin, l’intégrité globale du système est protégée par des mécanismes qui empêchent les modifications non autorisées du système d’exploitation.

Ces différentes couches de sécurité permettent de limiter les risques liés aux applications malveillantes.

---

## Étape 7 : Vérifier Android Verified Boot

Android Verified Boot est un mécanisme qui vérifie l’intégrité du système au moment du démarrage. Il fonctionne grâce à une chaîne de confiance où chaque composant vérifie l’authenticité du composant suivant.

L’objectif principal de ce mécanisme est de garantir que le système qui démarre est bien celui fourni par le fabricant et qu’il n’a pas été modifié.

Lors du laboratoire, l’état de Verified Boot peut être vérifié afin d’identifier si le système est considéré comme sécurisé ou modifié.

Les états possibles indiquent si le système est intact, modifié ou compromis.

---

## Étape 8 : Android Verified Boot (analyse)

Cette étape consiste à approfondir la compréhension du mécanisme Android Verified Boot. Le système vérifie l’intégrité des partitions système et empêche le chargement d’un système modifié non autorisé.

Lorsque le bootloader détecte une modification, l’état du système change et un avertissement peut apparaître. Cela permet d’alerter l’utilisateur que l’intégrité du système n’est plus garantie.

Cette protection est essentielle pour empêcher l’installation de logiciels malveillants au niveau du système.

---

## Étape 9 : Définir le rooting

Le rooting est une technique qui permet d’obtenir des privilèges administrateur sur un système Android. Cela donne un contrôle total sur le système d’exploitation et permet d’accéder à des fichiers ou des fonctions normalement protégés.

Bien que le rooting puisse être utilisé pour personnaliser le système ou réaliser des analyses de sécurité, il comporte également des risques importants. Il peut affaiblir les protections du système et exposer l’appareil à des attaques.

Dans un contexte de laboratoire, le rooting permet d’étudier le comportement des mécanismes de sécurité d’Android.

---

## Étape 10 : Intérêt du laboratoire

Ce laboratoire permet de comprendre comment les mécanismes de sécurité d’Android protègent l’intégrité du système et des applications.

Il permet également d’observer les conséquences de la désactivation de certaines protections, comme dans le cas du rooting.

Enfin, il offre une introduction pratique à l’analyse de sécurité mobile et aux concepts utilisés dans les audits de sécurité Android.

---

## Étape 11 : Matrice de risques

Le rooting peut introduire plusieurs risques pour la sécurité d’un appareil Android.

Parmi les risques possibles :
- accès non autorisé aux données sensibles
- installation d’applications malveillantes avec privilèges élevés
- modification du système d’exploitation
- contournement des mécanismes de sécurité
- perte d’intégrité du système
- désactivation des protections de sécurité
- exposition accrue aux attaques
- instabilité du système

Chaque risque doit être identifié et décrit afin de comprendre son impact potentiel.

---

## Étape 12 : Mesures défensives

Pour limiter les risques liés au rooting et aux modifications du système, plusieurs mesures peuvent être mises en place.

Par exemple :
- maintenir Android à jour
- utiliser des mécanismes de vérification d’intégrité
- limiter les privilèges des applications
- surveiller les comportements anormaux
- utiliser des solutions de sécurité mobile
- appliquer des politiques de sécurité strictes
- protéger l’accès au bootloader
- contrôler les applications installées

Ces mesures contribuent à renforcer la sécurité globale du système.

---

## Étape 13 : OWASP MASVS

Le standard OWASP Mobile Application Security Verification Standard (MASVS) définit un ensemble d’exigences pour améliorer la sécurité des applications mobiles.

Deux exigences importantes sont :
- la protection des données sensibles
- la vérification de l’intégrité de l’application et du système

Ces exigences permettent de garantir que l’application respecte les bonnes pratiques de sécurité mobile.

---

## Étape 14 : OWASP MASTG

Le guide OWASP Mobile Application Security Testing Guide (MASTG) fournit des recommandations pour tester la sécurité des applications mobiles.

Deux idées de tests possibles sont :
- vérifier si l’application détecte un appareil rooté
- analyser le stockage des données sensibles sur l’appareil

Ces tests permettent d’identifier les faiblesses potentielles dans la sécurité de l’application.

---

## Étape 15 : Commandes de rooting

Les commandes utilisées dans le laboratoire permettent d’activer les privilèges root et de modifier les partitions système dans l’émulateur Android.

Ces commandes permettent également de vérifier l’état du système et de confirmer que l’environnement de test est correctement configuré.

Elles servent principalement à reproduire un environnement Android modifié afin d’observer les réactions des mécanismes de sécurité.

---

## Étape 16 : Traçabilité et fiche environnement

Il est important de documenter l’environnement utilisé pour les tests.

Cette fiche doit contenir :
- le système d’exploitation utilisé
- la version d’Android de l’émulateur
- les outils utilisés (ADB, Android Studio)
- la configuration de l’AVD
- la version de l’application testée

Cette traçabilité permet de reproduire l’expérience et d’assurer la transparence du laboratoire.

---

## Étape 17 : Remise à zéro de l’AVD

À la fin du laboratoire, l’émulateur doit être réinitialisé afin de supprimer toutes les modifications réalisées pendant les tests.

Cela permet de restaurer un environnement propre et d’éviter que les modifications ne persistent pour les expériences futures.

---

## Étape 18 : Remise à zéro du device de laboratoire

Si un appareil physique de laboratoire a été utilisé, il doit également être réinitialisé afin de supprimer les modifications système et restaurer la configuration d’origine.

Cette étape est importante pour garantir la sécurité et l’intégrité de l’appareil.

---

## Étape 19 : Livrables

Le laboratoire doit être accompagné d’un rapport final qui résume les différentes étapes réalisées.

Le document doit inclure :
- la description de l’environnement de test
- les manipulations effectuées
- l’analyse des mécanismes de sécurité Android
- les risques identifiés
- les mesures de protection proposées
- les conclusions du laboratoire

Ce rapport permet de démontrer la compréhension des mécanismes de sécurité Android et des impacts du rooting.
