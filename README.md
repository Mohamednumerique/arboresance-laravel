# organisation-fichier-Laravel

# Framework= ensemble de fichiers

# Les dossiers

## app

Le dossier app est le dossier le plus important. C'est celui qui contiendra __l'application = tout  code PHP (fonctions, classes…).__

## bootstrap

Le dossier bootstrap n'est pas utile. __Il contient principalement des fichiers liés au lancement du framework ainsi qu'un dossier cache pour certaines optimisations.__

## config

Le dossier config permet la __configuration du framework.__ 

À l'intérieur, chaque fichier correspond à une fonctionnalité configurable. Par exemple, le fichier config/database.php contient un tableau PHP avec différentes valeurs de configuration pour l'URL de la base de données, l'utilisateur, le mot de passe…

## database

Le dossier database permet la __gestion de la base données.__

Le principal sous-dossier : sous-dossier migrations. 

__Les migrations sont des fichiers permettant de décrire votre base de données afin de permettre à Laravel de créer, modifier ou supprimer les tables et les colones automatiquement pour vous.__ Si vous avez déjà utilisé PHPMyAdmin, les migrations remplacent une partie l'utilisation de PHPMyAdmin.
Les sous-dossiers seeds et factories ne sont pas utiles pour le moment.

## public

Le dossier public contient __tous les fichiers accessibles directement par vos visiteurs.__

Par exemple, si vous avez des images publiques sur votre site, elles doivent être dans le dossier public (ou dans un sous-dossier du dossier public). Même chose pour vos fichiers CSS et JavaScript.

Laravel fournit de base quelques fichiers utiles comme un favicon, un fichier robots.txt…

__Le fichier index.php est la porte d'entrée de votre application. C'est le seul fichier PHP accessible de l'extérieur et il sera responsable de lancer le framework et d'appeler votre code situé dans le dossier app. Vous n'aurez jamais à modifier ce fichier directement car, comme dit précédemment, notre code PHP se trouve dans le dossier app.__

## resources


Le dossier resources contient de nombreuses choses diverses. __Principalement pour les autres fichiers de notre application qui ne sont pas du code PHP.__

__Le dossier resources/js et resources/sass contient des fichiers pré-CSS et pré-JS avant leur compilation.__ Si vous n'avez jamais compilé de fichier SASS, ni utilisé Babel, Webpack ou autre pour compiler votre JavaScript, passez votre chemin. Nous aurons tout le temps d'étudier ces concepts par la suite.

__Le dossier resources/lang contient les fichiers de traduction pour votre application. Ils ne vous seront utiles que si vous souhaitez créer un site multi-lingue.__

__Le dossier resources/views contient les vues de votre application.__ Les vues sont des fichiers majoritairement composés de HTML et sont chargés de la partie affichage de votre site. C'est l'un des dossiers les plus importants après le dossier app.

## routes

Si vous avez l'habitude d'une architecture PHP simple : https://mon-site.com/contact.php exécute le code situé dans contact.php et https://mon-site.com/compte.php exécute compte.php. Dans une architecture MVC comme celle de Laravel, toutes les requêtes des utilisateurs arrivent via le fichier public/index.php il est donc nécessaire de faire le lien entre l'URL entrée par le visiteur (« /contact », « /mon-compte »…) et le code qui sera exécuté. C'est dans le fichier routes/web.php que vous allez configurer ce lien. Nous verrons justement ça dans le prochain chapitre.
Si vous souhaitez développer une API, le fichier routes/api.php sera l'endroit où mettre vos liens. Si vous souhaitez mettre en place des actions en ligne de commande pour votre application, ce sera le fichier routes/console.php. Et si vous souhaitez envoyer des messages avec des websockets à vos visiteurs, ce sera le fichier routes/channel.php. Mais ces trois fichiers ne sont pas indispensable contrairement au fichier routes/web.php.

## storage

__Le dossier storage/app contient tous les fichiers générés par votre application,__ par exemple des factures PDF, les photos de profil de vos utilisateurs, etc.

__Le dossier storage/framework contient des fichiers utilisés uniquement par le framework.__ Il est recommandé de ne pas ajouter ou supprimer de fichiers à ce dossier.

Enfin,__le dossier storage/logs contient les fichiers de logs de votre application.__ Les fichiers de logs contiennent des informations sur l'activité de votre application. Par défaut, Laravel enregistrera dans un fichier storage/logs/laravel-YYYY-MM-DD.log tous les problèmes rencontrés par votre application : très utile pour comprendre pourquoi votre site ne fonctionne pas par exemple.

## tests

Les tests sont un __moyen rapide et automatisé de vérifier que votre application fonctionne comme vous le souhaitez.__ Si votre application commence à grossir, il est important de comprendre comment fonctionne les tests en programmation.

## vendor

Le dossier vendor __contient toutes les dépendances PHP téléchargées par Composer.__ Vous pouvez par exemple retrouver dans vendor/laravel/framework le code source de Laravel. Vous ne devez jamais changer les fichiers de ce dossier, car ces modifications seront écrasées par Composer à la prochaine mise à jour.

## Les fichiers

À la racine de notre projet, Composer a également ajouté de nombreux fichiers. La plupart sont des fichiers de configuration pour des outils externes (Git, Composer, NPM, PHPUnit…) et nous ne les utiliserons pas avant d'avoir découvert ces outils.


### .env


Les fichiers .env __contient les mots de passe de vos services ainsi que toutes les données sensibles de votre application (mot de passe de base de données, adresse de la base de données…).__ Ce fichier ne doit jamais être partagé. Afin de connaître les informations à renseigner, il existe un fichier .env.example qui contient uniquement des valeurs d'exemple.

### .gitattributes et .gitignore

Ces fichiers sont __utilisés par le logiciel Git.__

### artisan

Le fichier artisan __permet de lancer des commandes comme php artisan serve.__

### composer.json et composer.lock

Le fichier __composer.json contient toutes les dépendances requises par notre application.__ Le fichier __composer.lock est un fichier généré automatiquement par Composer lors de la commande composer update.__ ATTENTION: ne jamais le modifier manuellement.

### webpack.mix.js

Webpack est __un outil permettant de transformer des fichiers SASS en fichier CSS ou encore de compiler du JavaScript.__

### packages.json et yarn.lock

Le fichier __packages.json est identique au fichier composer.json en PHP mais pour le JavaScript avec l'outil NPM.__

### phpunit.xml

PHPUnit est un __outil qui permet de lancer les tests unitaires et fonctionnels.__ Ce fichier sera utile lorsque vous utilisez des tests dans le dossire tests.

### server.php

Le fichier server.php est __uniquement présent pour que la commande php artisan serve fonctionne.__ Vous ne devriez jamais avoir à y toucher.
