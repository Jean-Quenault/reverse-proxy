
# Reverse Proxy

This project sets up a Docker environment including an Nginx web server acting as a reverse proxy and several instances of a PHP application, managed using Docker Compose and Docker Swarm.

## Prerequisites

- Docker
- Docker Compose
- Docker Swarm (for deployment with replicas)

## Configuration

The project consists of two main services defined in `docker-compose.yml`:

1. `webserver`: An Nginx web server used as a reverse proxy.
2. `app`: A PHP application deployed with Apache, scaled across multiple instances.

## Installation

1. Clone the repository:

   ```
   git clone https://github.com/Jean-Quenault/reverse-proxy
   ```

2. Navigate to the project directory:

   ```
   cd reverse-proxy
   ```

## Deployment

### Docker Compose Mode

To launch the services in Docker Compose mode:

```
docker-compose up -d
```

### Docker Swarm Mode

If you are using Docker Swarm:

1. Initialize Docker Swarm (if not already done):

   ```
   docker swarm init
   ```

2. Deploy with Docker Stack:

   ```
   docker stack deploy -c docker-compose.yml [STACK_NAME]
   ```

### Service Scaling

To increase the number of replicas of the `app` service:

```
docker service scale [STACK_NAME]_app=[NUMBER_OF_REPLICAS]
```

## NGINX Configuration

Nginx configurations are located in the `./nginx` folder. You can modify them as needed.
