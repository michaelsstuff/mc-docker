# Minecraft Server in Docker

Run your minecraft server in a docker container.

## Usage

Create any of the following files if you want to customize your server:

`server.properties`

`banned-ips.json`

`banned-players.json`

`ops.json`

`whitelist.json`

Depending on the files you created, start the server:

```sh
docker run --rm -it -d \
-v my-mc-world:/mc/world \
-p 25565 \
--name my-mc-world \
-v $(pwd)/server.properties:/mc/server.properties \
-v $(pwd)/banned-ips.json:/mc/banned-ips.json \
-v $(pwd)/banned-players.json:/mc/banned-players.json \
-v $(pwd)/ops.json:/mc/ops.json \
-v $(pwd)/whitelist.json:/mc/whitelist.json \
michaelsstuff/mc-docker:latest
```

## Mods

TBA

### issuing server commands

`docker attach my-mc-world`

Now you have the minecraft server console open and can issue server commands.
To close this console enter

`Ctrl+p`, `Ctrl+q`
