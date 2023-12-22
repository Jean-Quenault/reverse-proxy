
# Projet Docker NGINX et PHP

Ce projet configure un environnement Docker comprenant un serveur web NGINX et plusieurs instances d'une application PHP, gérées à l'aide de Docker Compose et Docker Swarm.

## Prérequis

- Docker
- Docker Compose
- Docker Swarm (pour le déploiement avec des réplicas)

## Configuration

Le projet se compose de deux services principaux définis dans `docker-compose.yml` :

1. `webserver` : Un serveur web NGINX utilisé comme reverse proxy.
2. `app` : Une application PHP déployée avec Apache, scalée sur plusieurs instances.

## Installation

1. Cloner le dépôt :

   ```
   git clone [URL_DU_DEPOT]
   ```

2. Naviguer dans le répertoire du projet :

   ```
   cd [NOM_DU_REPERTOIRE]
   ```

## Déploiement

### Mode Docker Compose

Pour lancer les services en mode Docker Compose :

```
docker-compose up -d
```

### Mode Docker Swarm

Si vous utilisez Docker Swarm :

1. Initialiser Docker Swarm (si ce n'est pas déjà fait) :

   ```
   docker swarm init
   ```

2. Déployer avec Docker Stack :

   ```
   docker stack deploy -c docker-compose.yml [NOM_DU_STACK]
   ```

### Scaling des Services

Pour augmenter le nombre de réplicas du service `app` :

```
docker service scale [NOM_DU_STACK]_app=[NOMBRE_DE_REPLICAS]
```

## Configuration NGINX

Les configurations NGINX se trouvent dans le dossier `./nginx`. Vous pouvez les modifier selon vos besoins.

## Contribution

Pour contribuer à ce projet, veuillez créer une branche pour chaque fonctionnalité ou correction et soumettre une pull request pour chaque branche.

## Licence

[CHOISIR LA LICENCE APPROPRIÉE]

## Contact

[INFORMATIONS DE CONTACT]
