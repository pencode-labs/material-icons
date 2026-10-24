# Material Design Icons

A Pencode file icon theme based on [Material Icon Theme](https://github.com/material-extensions/vscode-material-icon-theme).

Uses the [Pencode](https://github.com/pencode-labs/pencode) peb v6 SDK. Requires Go 1.27.0 or newer.

## Build and install

```sh
git clone https://github.com/pencode-labs/material-icons.git
cd material-icons
go build -o bin/material-icons .
```

In Pencode's extension manager, choose **Install from local directory** and select this checkout. Extensions run on the workspace server, so build and install on that host for remote workspaces.

On Windows, build `bin/material-icons.exe` and set `entry` in `resources/extension.json` to `bin/material-icons.exe` before installing.

## Development

```sh
go test ./...
```

## License

MIT. See [LICENSE](LICENSE). The bundled icons retain the upstream [MIT license and copyright notice](resources/LICENSE.txt).
