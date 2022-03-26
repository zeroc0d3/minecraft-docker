## Minecraft Docker

Maincraft server with forge & mods.

### How-to-run

- Install Docker
- Install Docker-Compose
- Copy inside folder `data` to your binding container volume (eg: `/data`)
- Copy `.env.example` to `.env`
- Run:

  ```
  ./run-docker.sh
  ```

### Running Multiplayer

- Add Creative Server

  ```
  Server Name: Docker Creative
  Server Address: 172.145.145.6:25566
  ```

- Add Forge Server

  ```
  Server Name: Docker Forge (Survival)
  Server Address: 172.145.145.7:25567
  ```

- Add Survival Server

  ```
  Server Name: Docker Survival
  Server Address: 172.145.145.8:25568
  ```

### Advanced Configuration

- Change IP Address Server & Port

  ```
  default:
  - .env
    - CONTAINER_IP_MINECRAFT_CREATIVE=172.145.145.6
    - CONTAINER_IP_MINECRAFT_FORGE=172.145.145.7
    - CONTAINER_IP_MINECRAFT_SURVIVAL=172.145.145.8
    - PORT_MINECRAFT_CREATIVE=25566
    - PORT_MINECRAFT_FORGE=25567
    - PORT_MINECRAFT_SURVIVAL=25568

  - server-creative.properties
    - query.port=25566
    - rcon.port=25566
    - server-port=25566
    - server-ip=172.145.145.6

  - server-forge.properties
    - query.port=25567
    - rcon.port=25567
    - server-port=25567
    - server-ip=172.145.145.7

  - server-survival.properties
    - query.port=25568
    - rcon.port=25568
    - server-port=25568
    - server-ip=172.145.145.8
  ```

- Add Operator (Cheat Mode) User
  - ops.json

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

- Docker Version

  ```
  docker -v
  ---
  Docker version 19.03.5, build 633a0ea838
  ```

- Docker-Compose Version

  ```
  docker-compose -v
  ---
  docker-compose version 1.24.1, build 4667896b
  ```

### Version

- Server: `minecraft_server.1.18.2.jar`
- Forge: `forge-1.18.2-40.0.32.jar`
- Mods:
  - `lucky-block-forge-1.18.2-12.0.jar`

### License

MIT License
