# Devcontainer for Python

## Using within you project

Add `.devcontainer/devcontainer.json` to your repository.

```json
{
  "image": "ghcr.io/hspaans/angular-devcontainer:latest",
  "name": "Angular",
  "settings": {
    "terminal.integrated.shell.linux": "/bin/bash"
  },
  "appPort": [],
  "postCreateCommand": "",
  "remoteUser": "node",
  "extensions": [
    "github.vscode-pull-request-github",
    "angular.ng-template",
    "ms-vscode.vscode-typescript-tslint-plugin",
    "redhat.vscode-yaml",
    "ms-vscode.vscode-typescript-next"
  ]
}
```
