# spring-boot-microservices-boilerplate

A starter for Spring Boot microservices with an API gateway, service discovery and centralized configuration, deployable with Docker Compose.

## Services
| Service | Port | Role |
|---|---|---|
| `api-gateway` | 8080 | Single entry point (Netflix Zuul) |
| `discovery-service` | 8761 | Eureka service registry |
| `config-service` | 8888 | Spring Cloud Config server |

The config-service reads its configuration from [spring-boot-microservice-cloud-config](https://github.com/gillioa/spring-boot-microservice-cloud-config) over SSH, so it needs SSH access to GitHub.

## Requirements
Java 8, Maven, Docker and docker-compose. The services use Spring Boot 2.0.1 and Spring Cloud Finchley.M8.

## Run
```bash
./dockerize.sh deploy -c    # compile every jar, build images, start containers
```
| Command | Effect |
|---|---|
| `deploy` | Build images and start without recompiling |
| `deploy -c` | Compile, build and start |
| `compile` | Compile the jars only |
| `images` / `images -c` | Build images (optionally compile first) |
| `clean` | Remove the containers and images |

The Spring profile defaults to `docker` (override with `SPRING_PROFILES_ACTIVE`).

## Status
Archived. Based on Java 8, Spring Boot 2.0.1, Spring Cloud Finchley (milestone) and Zuul 1, all end-of-life.

## License
MIT