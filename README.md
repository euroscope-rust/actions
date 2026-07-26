# GitHub actions to work with EuroScope

This repo contains various GitHub actions for EuroScope.

Examples show retrieving actions from the `main` branch, but you should really
pin your dependencies to a specific hash.

## `install`

This action installs EuroScope on a Windows runner.

### `install` usage

```yaml
- name: Install EuroScope
  uses: euroscope-rust/actions/install@main
  with:
    version: latest
```

### `install` inputs

The following inputs are available for `install`:

| Input | Description |
| --- | --- |
| `version` | The EuroScope version to install, e.g. `"3.2.13"`. Set to `latest` to install the newest released version. Defaults to `"latest"`. Only the version currently published on EuroScope's website can be installed; older versions are not hosted. |
| `cache` | Whether to cache the downloaded installer. Set to `"false"` to always fetch fresh. Defaults to `"true"`. |

### `install` outputs

The following outputs are available for `install`:

| Output | Description |
| --- | --- |
| `version` | The EuroScope version that was installed. Same as the `version` input, except when it was `latest`, in which case this is the resolved version. |

## License

See [LICENSE](./LICENSE).

## Contributing

Just open a PR.

## Releasing

Create a new GitHub release.