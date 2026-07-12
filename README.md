# GitHub actions to work with EuroScope

This repo contains various GitHub actions for EuroScope.

Examples show retrieving actions from the `main` branch, but you should really
pin your dependencies to a specific hash.

## `list-versions`

This action lists the available EuroScope versions.

### `list-versions` usage

```yaml
- name: List EuroScope versions
  uses: euroscope-rust/actions/list-versions@main
  with:
    version-families: |
      3.1
      3.2
```

### `list-versions` inputs

The following inputs are available for `list-versions`:

| Input | Description |
| --- | --- |
| `version-families` | An optional newline-separated list of version families to filter for. |
| `cache` | Whether to cache the retrieved list. The list is cached for 1 day. Defaults to `"true"`. Set to `"false"` to disable the cache. |
| `limit` | Maximum number of release posts to inspect from the EuroScope website. |

### `list-versions` outputs

The following outputs are available for `list-versions`:

| Output | Description |
| --- | --- |
| `versions` | JSON array of all discovered version strings, newest release first. |
| `latest` | The most recently released version string. |
| `count` | Number of versions discovered. |

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

The `install` action has no outputs.

## License

See [LICENSE](./LICENSE).

## Contributing

Just open a PR.

## Releasing

Create a new GitHub release.