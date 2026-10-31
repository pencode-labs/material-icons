# Material Design Icons

A Pencode file icon theme based on [Material Icon Theme](https://github.com/material-extensions/vscode-material-icon-theme).

Uses the [Pencode](https://github.com/pencode-labs/pencode) peb v14 SDK. Requires Go 1.27.0 or newer.

## Build and install

```sh
git clone git@github.com:pencode-labs/material-icons.git
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

## Releases

Push a `v*` tag (for example, `v1.0.0`) to this repository, or publish a GitHub Release,
to test and build Linux, macOS and Windows packages for amd64 and arm64. The workflow
uploads ZIP archives and `SHA256SUMS` to the matching release, creating it if needed.
Prerelease tags such as `v1.0.0-rc.1` create prereleases.

Each ZIP contains `bin/`, `resources/`, the README and license. Its manifest uses the
tag version and the correct executable suffix for Windows. Download the package
for the workspace server's OS and architecture, extract it, then install the
extracted directory through Pencode's extension manager.
