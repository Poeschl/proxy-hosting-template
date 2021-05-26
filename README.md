# Proxy Hosting Template

During setup for a new project of mine, I need to setup some infrastructure for host monitoring and a reverse proxy with auth.
This all will be realized in docker to have as less dependencies as possible.

( 💭 Better name pending.... )

## Requirements on the system

I will use that repository on linux based hosts und require a full docker and docker-compose installation on it.
Instructions to install docker can be found [here](https://docs.docker.com/engine/install/#server).

## Endpoints

TBD: List all endpoints and paths.

## Architecture

TBD: Draw diagram

The architecture includes [Glances](https://github.com/nicolargo/glances) to monitor the system conditions.
It offers a prometheus interface which will be scraped by (obviously) Prometeus.
Which will be accessed by a Grafana installation, which is available from the outside.
To allow access to the services included and others as well Traefik manages the http(s) ports.

In this template traefik authenticate the endpoints with GitHub OAuth.
So when accessing protected services the user is asked to login into GitHub first.

## Traefik Setup

As reverse proxy [Traefik](https://doc.traefik.io/traefik/) is used.
With its label-based configuration it's easy to extend it to services outside of this repository.

### Lets Encrypt

//TBD

### Include other services to Traefik

TBD: docker-compose.override.yaml

## Grafana

TBD: Image Dashboard

Grafana will be provisioned with Prometeus and a basic dashboard which monitor the host system.
