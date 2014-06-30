[Web Services @ ESGI [FR]](https://github.com/rhannequin/ws-docs)
=======

Ceci est le répertoire de documentation du projet Webservices & XML de l'ESGI,
présenté par Bastian PEGHAIRE, Hervé TRAN et Rémy HANNEQUIN.

Ce projet est réparti en quatre services distincts :

- [ws-soap-server](https://github.com/2slow/ws-soap-server) : serveur SOAP en PHP
- [ws-rest-server](https://github.com/Jagbomb/ws-rest-server) : serveur REST en NodeJS
- [ws-app](https://github.com/rhannequin/ws-app) : service principal en Ruby
- [ws-client](https://github.com/rhannequin/ws-client) : application cliente en HTML / CSS / JavaScript

## Pré-requis

- NodeJS / NPM
- PHP 5
- Ruby 2.1

## Installation

    git clone https://github.com/2slow/ws-soap-server.git
    git clone https://github.com/Jagbomb/ws-rest-server
    git clone https://github.com/rhannequin/ws-app
    git clone https://github.com/rhannequin/ws-client
    cd ws-rest-server
    npm install
    cd ../ws-app
    bundle install
    cd ../ws-client
    npm install

N'oubliez pas d'utiliser le fichier [places.sql](https://github.com/Jagbomb/ws-rest-server/blob/master/db/places.sql) pour remplir votre base de données MySQL `places`.

## Lancement

Vérifiez que la ligne 34 au fichier `ws-app/app.rb` indique bien l'URL d'où est accessible votre service `ws-soap-server`. Assurez-vous également qu'Apache aura bien les droits de lecture et écriture sur le fichier `ws-soap-server/data/comments.xml`.

Vérifiez également que les ports `3000`, `5000` et `4242` sont libres. Ces ports sont ceux utilisés par défaut par les différents services.

### Serveur REST

    cd ws-rest-server
    node app.js

### Application

    cd ws-app
    foreman start

### Client browser

    cd ws-client
    gulp

L'application devrait maintenant s'ouvrir automatiquement dans votre navigateur.


## Documentation

Il est possible d'afficher la documentation de l'application principale qui est consommée par le client browser. Il suffit de lancer un serveur web dans ce dossier-même, avec python par exemple :

    python -c 'import SimpleHTTPServer; SimpleHTTPServer.test()'

Et d'ouvrir la page [http://localhost:8000](http://localhost:8000).
