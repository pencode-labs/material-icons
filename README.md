# Material Design Icons

A Pencode file icon theme based on [Material Icon Theme](https://github.com/material-extensions/vscode-material-icon-theme).

Uses the [Pencode](https://github.com/pencode-labs/pencode) peb v20 SDK. Requires Go 1.27.0 or newer.

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

Push a version tag such as `v0.1.0` to test, cross-compile and publish a GitHub
Release automatically. Linux, macOS (`darwin`) and Windows each support `amd64`
and `arm64`. Prerelease tags such as `v0.2.0-rc.1` create prereleases.

Assets use `<extension-id>-<tag>-<os>-<arch>.zip`, accompanied by `SHA256SUMS`.
Each ZIP has one top-level `<extension-id>/` directory containing `bin/`,
`resources/extension.json`, the README, license and all resource notices. The
packaged manifest uses the tag version and Windows entries include `.exe`.

Download the archive matching the **workspace server's** OS and architecture.
Extract it directly into `~/.pencode/extensions/` (Windows:
`%USERPROFILE%/.pencode/extensions/`), preserving executable permissions. For
example, `unzip material-icons-v0.1.0-linux-amd64.zip -d ~/.pencode/extensions/` installs
`~/.pencode/extensions/material-icons/resources/extension.json`. Restart Pencode to discover the extension.
For remote workspaces, extract on the remote server. You can also select the
extracted `<extension-id>/` directory in the extension manager's local-directory
installation flow. No Go toolchain is needed to use a release package; extension
specific tools described above still need to be available on the workspace server.
