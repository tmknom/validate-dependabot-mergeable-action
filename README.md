# validate-dependabot-mergeable-action

Validate the mergeability of a Dependabot pull request.

<!-- actdocs start -->

## Description

This action determines whether a Dependabot pull request can be merged based on the specified update type.

## Usage

```yaml
  steps:
    - name: Validate Dependabot Mergeable
      uses: tmknom/validate-dependabot-mergeable-action@v0
```

## Inputs

| Name | Description | Default | Required |
| :--- | :---------- | :------ | :------: |
| major | Whether to merge the major version. | n/a | yes |
| minor | Whether to merge the minor version. | n/a | yes |
| patch | Whether to merge the patch version. | n/a | yes |
| update-type | The type of semantic versioning update. Acceptable values are `version-update:semver-patch`, `version-update:semver-minor`, and `version-update:semver-major`. | n/a | yes |

## Outputs

| Name | Description |
| :--- | :---------- |
| mergeable | Indicates whether the update type is mergeable. |

<!-- actdocs end -->

## Permissions

N/A

## FAQ

### What is the `update-type`?

The `update-type` defines which semantic version updates Dependabot should include.
Semantic versioning (in the form `x.y.z`) is a standard for specifying software versions, where:

- `x`: Represents the major version
- `y`: Represents the minor version
- `z`: Represents the patch version

Dependabot uses these rules to decide which versions to update.
Supported `update-type` values are:

- **`version-update:semver-patch`**: Includes patch updates (e.g., `1.0.0` → `1.0.1`).
- **`version-update:semver-minor`**: Includes minor updates (e.g., `1.0.0` → `1.1.0`).
- **`version-update:semver-major`**: Includes major updates (e.g., `1.0.0` → `2.0.0`).

For more details, see: [Dependabot options reference][update_type].

## Related projects

- [merge-workflows](https://github.com/tmknom/merge-workflows): Collection of merge workflows.

## Release notes

See [GitHub Releases][releases].

[update_type]: https://docs.github.com/en/code-security/dependabot/working-with-dependabot/dependabot-options-reference#update-types-ignore
[releases]: https://github.com/tmknom/validate-dependabot-mergeable-action/releases
