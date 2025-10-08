# Command failed: install-tool pnpm 10.17.0 #38237

## Current behaviour

When using pnpm `configDependencies` values in _pnpm-workspace.yaml_ the renovate pnpm install (`install-tool pnpm {version}`) fails and PRs are not automatically created.

This reproduction uses `@pnpm/plugin-better-defaults` as a config dependency which runs pnpm install hooks, however, any value for `configDependencies` will cause this issue.

## Expected behaviour

The pnpm install in renovate should pass successfully and branches should continue to be created.

`configDependencies` hooks may or may not be run, but having them in the pnpm-workspace should at least not break the renovate install.

## Link to the Renovate issue or Discussion

https://github.com/renovatebot/renovate/discussions/38237
