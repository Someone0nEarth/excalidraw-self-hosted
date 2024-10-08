# Self-Hosted excalidraw

The goal is a docker-compose configuration for a fully self-hosted [Excalidraw](https://github.com/excalidraw/excalidraw) with collaboration support. The configuration is for a [traefik](https://github.com/traefik/traefik) setup and uses a [MongoDB](https://github.com/mongodb/mongo) for the storage. Also includes [mongo-express](https://github.com/mongo-express/mongo-express) as a MongoDB admin interface.

The original version of excalidraw only supporting Firebase for the storage. For achieving a self-hosted storage, a modified version of excalidraw is used:

- <https://github.com/alswl/excalidraw>

In combination with a http-storage:

- <https://github.com/alswl/excalidraw-storage-backend>

## Prerequisites

- Docker / Docker Compose
- A traefik setup with a configured https entrypoint

## Deploy

Clone this repository: `git clone git@github.com:Someone0nEarth/excalidraw-self-hosted.git`

Create a copy of the env-example: `cp .env-example .env` and modifying the `.env` with your values.

Pull the images and start the containers: `docker-compose up -d`

## Usage

Open the excalidraw app in your browser with the host you configured for `APP_HOST`, for example: `https://excalidraw.your-domain.net`

The mongo-express can be reached under the host you configured for `MONGOEXPRESS_HOST`, for example: `https://excalidraw-db.your-domain.net`

## Current Limitations

The "Export" function to the [Excalidraw+ workspace](https://plus.excalidraw.com/) is not working/supported. Also there is no solution for self-hosting your own workspace yet.

## Other Self-Hosted Solutions/Attemps

- <https://github.com/alswl/excalidraw-collaboration> (although providing a docker-compose example for a nginx setup)
- <https://github.com/cocreators-ee/excalidraw-alternative-store>

Have fun,

someone.earth
