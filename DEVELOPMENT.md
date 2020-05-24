# Angular Development

## Create new application

Create a new Angular app called `appName` in the current directory

```shell
$ ng new appName --directory ./
```

## Enable TSLint in VSCode

Enable the `tslint` extension in `.devcontainer/devcontainer.json`

```json
...
	"extensions": [
		"ms-vscode.vscode-typescript-tslint-plugin"
    ]
...
```

Install modules for `tslint` with `npm`

```shell
$ npm install --save-dev typescript-tslint-plugin typescript
...
+ typescript@3.8.3
+ typescript-tslint-plugin@0.5.5
added 9 packages from 7 contributors, removed 1 package, updated 1 package and audited 1440 packages in 12.684s

50 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
$
```