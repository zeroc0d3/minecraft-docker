## Minecraft Docker

Maincraft server with forge & mods.

### How-to-run
* Install Docker
* Install Docker-Compose
* Copy inside folder `data` to your binding container volume (eg: `/data`)
* Copy `.env.example` to `.env`
* Run:
  ```
  bash run-docker.sh
  ```

### Running Multiplayer
* Add Creative Server
  ```
  Server Name: Docker Creative
  Server Address: 172.145.145.6:25565
  ```
* Add Survival Server
  ```
  Server Name: Docker Survival
  Server Address: 172.145.145.7:25525
  ```
* Add Forge Server
  ```
  Server Name: Docker Forge (Survival)
  Server Address: 172.145.145.8:25535
  ```

### Advanced Configuration
* Change IP Address Server & Port
  ```
  default:
  * .env
    - CONTAINER_IP_MINECRAFT_CREATIVE=172.145.145.6
    - CONTAINER_IP_MINECRAFT_SURVIVAL=172.145.145.7
    - CONTAINER_IP_MINECRAFT_FORGE=172.145.145.8
    - PORT_MINECRAFT_CREATIVE=25565
    - PORT_MINECRAFT_SURVIVAL=25525
    - PORT_MINECRAFT_FORGE=25535

  * server-creative.properties
    - query.port=25565
    - rcon.port=25565
    - server-port=25565
    - server-ip=172.145.145.6

  * server-survival.properties
    - query.port=25525
    - rcon.port=25525
    - server-port=25525
    - server-ip=172.145.145.7

  * server-forge.properties
    - query.port=25535
    - rcon.port=25535
    - server-port=25535
    - server-ip=172.145.145.8
  ```

* Add Operator (Cheat Mode) User
  * ops.json
    ```
    [
        {
            "uuid": "YOUR_UUID",
            "name": "YOUR_USERNAME",
            "level": 4,
            "bypassesPlayerLimit": false
        }
    ]
    ```

### Environment Test
* Docker Version
  ```
  docker -v
  ---
  Docker version 19.03.5, build 633a0ea838
  ```

* Docker-Compose Version
  ```
  docker-compose -v
  ---
  docker-compose version 1.24.1, build 4667896b
  ```

### Version
* Server: `minecraft_server.1.15.2.jar`
* Forge: `forge-1.15.2-31.1.12.jar`
* Mods:
  * `luckyblock-1.15.2-1.jar`

### License
MIT License
