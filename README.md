# github_fetchfile

Utility to fetch files from public/private repos. Written in Bash. These scripts authenticate to github by using a Personal Authentication Token, this makes it possible for these to work as you, even if you have 2-factor authentication.

## Features

- `github_token` -- a simple utility that will lookup and return tokens stored in your keychain. If the token isn't available, then it will open github's settings page for you to register one, and it will save it into your keychain on your behalf.
- `github_fetchfile_small` -- a utility that will fetch a file from github, as your user. This is limited to 1MB files.
- `github_fetchfile` -- a utility that will fetch any sized file from github, as your user. [WIP]

## Installation

Copy `github_token` and one or both of (`github_fetchfile`, `github_fetchfile_small`) into your $PATH somewhere, in the same directory, or embed these in a scripts directory.

## Usage

Each command will print a usage line if run with no arguments.

```
$ github_token
Usage: ./github_token -r -s SERVICE_NAME
	-r: request repo-level access

$ github_fetchfile[_small]
Usage: ./github_fetchfile[_small] [-t TOKEN] [-s SCRIPT_NAME] [-o REPO_OWNER] -r REPO [-b BRANCH] -p ASSET_PATH -O OUTPUT_PATH
 -t Github Personal Access Token with sufficient permissions. Will look at keychain if omitted.
 -s Identifier for the Keychain item used to lookup a token for this script.
```

