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

### Play Multiplayer
* Add Creative Server
  ```
  Server Name: Docker Creative
  Server Address: 172.130.130.6:25515
  ```
* Add Survival Server
  ```
  Server Name: Docker Survival
  Server Address: 172.130.130.7:25525
  ```

### Advanced Configuration
* Change IP Address Server & Port
  ```
  default:
  * .env
    - CONTAINER_IP_MINECRAFT_CREATIVE=172.130.130.6
    - CONTAINER_IP_MINECRAFT_SURVIVAL=172.130.130.7
    - PORT_MINECRAFT_CREATIVE=25515
    - PORT_MINECRAFT_SURVIVAL=25525

  * server-creative.properties
    - query.port=25515
    - rcon.port=25515
    - server-port=25515
    - server-ip=172.130.130.6

  * server-survival.properties
    - query.port=25525
    - rcon.port=25525
    - server-port=25525
    - server-ip=172.130.130.7
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
