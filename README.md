# Minecraft

## Upgrade and recovery

- Download world snapshot
- Extract snapshot into restore/
  - `rm -rf restore`
  - `tar fx world-yyyymmdd-hhiiss.tgz -C restore/`
- Update base image
  - `docker-compose pull mc`
- Clean volumes
  - `docker-compose down -v`
- Start minecraft-server with restore image
  - `docker-compose up -d`
- Pray
  - `docker-compose logs -f --tail=10 mc`

## RCON

`docker exec -i CONTAINER_ID rcon-cli`
