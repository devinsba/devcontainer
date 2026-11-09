# devcontainer

Dev containers for use with [DevPod](https://devpod.sh), built as two images so changes to the tools
don't rebuild the base:

- `base/` → `ghcr.io/devinsba/devcontainer/base` (Debian, Node, Python, uv, Terraform, kubectl/helm)
- `tools/` → `ghcr.io/devinsba/devcontainer/tools` (built on `base`; Claude Code, 1Password CLI)

```sh
devpod up github.com/devinsba/devcontainer --devcontainer-path tools/.devcontainer.json
```

`main` publishes `:latest`; pull requests publish `:pr-<number>` (tools builds on that PR's base) and
delete them when the PR closes.
