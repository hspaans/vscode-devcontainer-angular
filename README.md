# Devcontainer for Angular

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

## Versions

The container is based on [LTS](https://en.wikipedia.org/wiki/Long-term_support) distribution versions with official support and fall within N and N-2. The *latest*-tag is an experimental tag to test future releases.

| Platform | Version |                               Image                                |
| :------: | :-----: | :----------------------------------------------------------------: |
| Angular  |    9    |   [hspaans/angular-devcontainer:7.3(.x)][angular-devcontainer:9]   |
| Angular  |   10    |  [hspaans/angular-devcontainer:7.4(.x)][angular-devcontainer:10]   |
| Angular  |   11    |  [hspaans/angular-devcontainer:8.0(.x)][angular-devcontainer:11]   |
| Angular  |   11    | [hspaans/angular-devcontainer:latest][angular-devcontainer:latest] |

[angular-devcontainer:latest]: ghcr.io/hspaans/angular-devcontainer:latest
[angular-devcontainer:9]: ghcr.io/hspaans/angular-devcontainer:9
[angular-devcontainer:10]: ghcr.io/hspaans/angular-devcontainer:10
[angular-devcontainer:11]: ghcr.io/hspaans/angular-devcontainer:11
