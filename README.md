# Operator UI

This package is responsible for rendering the UI of the plugin node, which allows interactions wtih node jobs, jobs runs, configuration and any other related tasks.

## Setup

The GQL schema that lives within `GoPlugin/pluginV2` is used to generate client typings for this repo. See below for a list of options for generating these bindings, either based on a local plugin repo copy, or remotely off of github.

```sh
# Assuming that your plugin repo lives in ../chainlink (relative to this git repo root)
yarn setup

# If you have your plugin repo in a different directory
REPO_PATH="$HOME/src/GoPlugin/pluginV2" yarn setup

# If you want to fetch the schema files from github instead, from the develop branch
# Note that you need to supply $GH_TOKEN, this is a PAT that needs read access to the
# GoPlugin/pluginV2 repo.
GH_TOKEN=$GH_TOKEN yarn setup

# If you want a different branch than develop on the GoPlugin/pluginV2 repo
GH_TOKEN=$GH_TOKEN REPO_REF="feature/gql_changes" yarn setup
```

## Running Plugin Node

Assuming you already have a local plugin node listening on port 6688, run:

```
PLUGIN_BASEURL=http://localhost:6688 yarn start
```

Now navigate to http://localhost:3000.

If sign-in doesn't work, check your network console, it's probably a CORS issue. You may need to run your plugin node with `ALLOW_ORIGINS=http://localhost:3000` set.

## Running Tests

```
yarn test
```
