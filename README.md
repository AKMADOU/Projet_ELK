# Nom du Projet

## Description
[Décrivez brièvement le projet ici. Expliquez son objectif, ses fonctionnalités principales, et ce qu'il résout. Par exemple, si votre projet est un pipeline de données pour Logstash, vous pouvez expliquer son rôle dans l'ingestion et le traitement des logs.]

### Fonctionnalités
- Traitement des logs Nginx avec Logstash.
- Envoi des logs traités dans Elasticsearch.
- Visualisation des données dans Kibana.
- Filtrage et extraction d'informations via des expressions régulières (Grok).

## Prérequis

Avant de commencer, assurez-vous d'avoir les logiciels suivants installés sur votre machine :

- Docker et Docker Compose
- Elasticsearch (version 8.x ou plus récente)
- Logstash (version 8.x ou plus récente)
- Kibana (version 8.x ou plus récente)

Si vous n'avez pas ces outils installés, vous pouvez suivre les guides de leurs pages respectives pour l'installation.

## Installation

### 1. Cloner le dépôt

Clonez ce dépôt sur votre machine locale :


- git clone https://github.com/votre-nom-utilisateur/votre-repository.git
- cd votre-repository
### 2. Lancer les conteneurs Docker
Une fois dans le répertoire du projet, lancez les conteneurs Docker avec Docker Compose :


- docker-compose up -d
Cela démarrera les services suivants dans des conteneurs Docker :

- Elasticsearch : Serveur de recherche et d'analyse.
- Kibana : Interface graphique pour explorer et visualiser les données dans Elasticsearch.
- Logstash : Outil de traitement des logs, configuré pour ingérer et envoyer les logs dans Elasticsearch.
### 3. Vérifier le statut des services
Pour vérifier que les services sont bien lancés, vous pouvez utiliser la commande suivante pour voir les logs des conteneurs :


- docker-compose logs -f
Une fois que tout est en place, accédez à Kibana via http://localhost:5601 et à Elasticsearch via http://localhost:9200.

Configuration

Logstash
Le fichier de configuration de Logstash est situé dans le dossier ./logstash_dir/logstash.conf.

Assurez-vous de mettre à jour le chemin du fichier inlog.log pour qu'il pointe vers votre fichier de log réel.

Kibana
Une fois les logs envoyés à Elasticsearch, vous pouvez configurer un tableau de bord dans Kibana pour visualiser vos données. Utilisez le tableau de bord par défaut ou créez un nouveau tableau de bord en fonction de vos besoins.

Utilisation

Visualisation des logs
Accédez à Kibana à l'adresse http://localhost:5601.
Allez dans l'onglet Discover pour explorer vos logs.
Créez un index pattern nginx-logs-* pour voir les logs de votre application.
Commandes Docker
Voici quelques commandes utiles pour gérer votre environnement Docker :

Démarrer les services : 
- docker-compose up -d
Arrêter les services : 
- docker-compose down
Vérifier les logs : 
- docker-compose logs -f
Accéder aux conteneurs : 
- docker exec -it <container_name> bash
