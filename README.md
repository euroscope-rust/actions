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

## License

See [](./LICENSE).

## Contributing

Just open a PR.

## Releasing

Create a new GitHub release.