# @smartcontractkit/operator-ui

## 0.8.0

### Minor Changes

- bd8ff94: rename fromAddress to fromAddresses in blockhashStoreSpec
- bd8ff94: Remove the `maxGasPriceGWei` field from VRF job details page.
- bd8ff94: Add ability to show TOML config

  On the configuration screen, the user is now able to view their node's TOML config

- bd8ff94: Replaced "ETH balance" with "Native token balance"
- bd8ff94: Display the Feeds Manager navigation in the mobile navigation drawer

### Patch Changes

- bd8ff94: Show node type
- bd8ff94: Fixes task run status display for unfinished tasks
- bd8ff94: Display the name of job proposals in Feeds Manager
- bd8ff94: Fixes infinite loop issue on Sign Out
- bd8ff94: Fix bug preventing selection of "Rows per page" in jobs/ID/runs page
- bd8ff94: dynamic config for legacy vs. TOML; syntax highlighting; expansion panels

## 0.7.0

### Minor Changes

- d5517c9: Swap out compiler for testing and building for swc

  Using swc leads to significant performance gains in both CI and CD, with a 60% reduction in webpack build times, and a 25% reduction in test times.

  - Update to latest tsc version
  - Use swc for jest tests instead of ts-jest
  - Use swc for webpack builds
  - Update jest dependencies
  - Update jest snapshots based on JSON parsing changes in jsdom upgrade
  - Update gitignore to exclude yarn error logs
  - Fix serve config
  - Remove unused autobind decorator

- c6c81c1: Add "Key Admin Override" modal

  The `/keys` page in Operator UI now exposes several admin commands, namely:

  - An "abandon" checkbox to abandon all current transactions
  - Enable/disable a key for a given chain
  - Manually set the nonce for a key.

  See [this PR](https://github.com/smartcontractkit/chainlink/pull/7406) for a screenshot example.

- 1ab4990: Fetch chainlink node build info during runtime

  Previously, the chainlink version and commit sha were baked into the static assets. Now, they're fetched during runtime via the `/v2/build_info` endpoint after the user has logged in. This enables the operator ui build phase to be isolated from the chainlink build phase, as we no longer need to know the version and commit sha of the chainlink node ahead of time.
