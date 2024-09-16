# Core Keeper Dedicated Server Helm Chart

Based on: https://github.com/escapingnetwork/core-keeper-dedicated

Helm chart to deploy Core Keeper dedicated server

## Usage

1. Add helm chart:

```
helm repo add dqle https://dqle.io/helm-charts/
helm repo update
```

2. Install helm chart (with values.yaml file):
```
helm install core-keeper-dedicated-server dqle/core-keeper-dedicated-server -f values.yaml -n core-keeper-dedicated-server --create-namespace
```

## Configuration

values.yaml env args:

```
env:
  WORLD_INDEX: "0"
  WORLD_NAME: "Core Keeper Server"
  WORLD_SEED: "0"
  WORLD_MODE: "0"
  GAME_ID: ""
  DATA_PATH: "/home/steam/core-keeper-data"
  MAX_PLAYERS: "10"
  DISCORD: "0"
  DISCORD_HOOK: "https://discord.com/api/webhooks/{id}/{token}"
  SEASON: "-1"
  SERVER_IP: ""
  SERVER_PORT: ""
```

These are the arguments you can use to customize server behavior with default values.

```
WORLD_INDEX         Which world index to use.
WORLD_NAME          The name to use for the server.
WORLD_SEED          The seed to use for a new world. Set to 0 to generate random seed.
WORLD_MODE          Sets the world mode for the world. Can be Normal (0), Hard (1), Creative (2), Casual (4). NOTE: Changing between Creative and non-Creative worlds not currently supported.
GAME_ID             Game ID to use for the server. Need to be at least 28 characters and alphanumeric, excluding Y,y,x,0,O. Empty or not valid means a new ID will be generated at start.
DATA_PATH           Save file location. If not set it defaults to a sub-folder named "DedicatedServer" at the default Core Keeper save location.
MAX_PLAYERS         Maximum number of players that will be allowed to connect to server.
DISCORD             Enables discord webhook features witch sends GameID to a channel.
DISCORD_HOOK        Webhook url (Edit channel > Integrations > Create Webhook).
SEASON              Overrides current season by setting to any of None (0), Easter (1), Halloween (2), Christmas (3), Valentine (4), Anniversary (5), CherryBlossom (6), LunarNewYear(7). -1 is default setting where it is set depending on system date.
SERVER_IP           Only used if port is set. Sets the address that the server will bind to.
SERVER_PORT         What port to bind to. If not set, then the server will use the Steam relay network. If set the clients will connect to the server directly and the port needs to be open.
```