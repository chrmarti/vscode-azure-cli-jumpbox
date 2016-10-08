# Azure CLI Jumpbox

Docker image for the [Azure CLI](https://github.com/chrmarti/vscode-azure-cli) extension for VS Code.

## Development Notes

### Build

```
docker build -t chrmarti/azure-cli-jumpbox .
```

### Start

```
docker run --name azure-cli-jumpbox  -d -t -v /var/run/docker.sock:/var/run/docker.sock chrmarti/azure-cli-jumpbox cat
```

### Exec

```
docker exec -it azure-cli-jumpbox tmux new-session -s 'Azure CLI'
```

### Inspect

```
docker exec -it azure-cli-jumpbox tmux start-server\; list-sessions -F '#{session_name}'
```

### Reconnect

```
docker exec -it azure-cli-jumpbox tmux attach-session -t 'Azure CLI'
```
