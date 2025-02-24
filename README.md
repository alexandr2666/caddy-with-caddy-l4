# Caddy with caddy-l4 Plugin
This project automates the process of building a custom version of Caddy with the caddy-l4 plugin using GitHub Actions. The workflow compiles the binary and creates a GitHub Release with the built artifact.

## Features
Builds Caddy with the caddy-l4 plugin for Layer 4 proxy support.

Supports building the latest Caddy release or a specific version.

Automated check new caddy version every hour and build release if a new version is detected.

Manual builds via GitHub Actions workflow dispatch.

Releases include the compiled binary as an artifact.

## Manual Builds
Go to the Actions tab in this repository.

Select the Build Custom Caddy with Layer4 workflow.

Click Run workflow.

### Optionally specify:

version: The Caddy version to build (default: latest).

tag: A custom tag for the Release (optional).

Once completed, download the binary from the generated Release.


## Workflow Details

Trigger: Manual (workflow_dispatch) or scheduled (cron: "0 3 * * 3").

Build Process:
Uses xcaddy to compile Caddy with the caddy-l4 plugin.
Go version: 1.24.
Runs on ubuntu-latest.
Output: A single caddy binary uploaded as a Release asset.

## Prerequisites

A GitHub repository with this workflow configured.

The GITHUB_TOKEN with contents: write permissions (automatically provided by GitHub Actions).

How It Works

The workflow checks for the latest Caddy release or uses the specified version.

It builds the custom Caddy binary with the caddy-l4 plugin using xcaddy.

The binary is uploaded as an artifact and attached to a new GitHub Release.

Note: The Caddy server and caddy-l4 plugin follow their own respective licenses.

## Acknowledgments

[Caddy](https://github.com/caddyserver/caddy) - A powerful, extensible web server.

[caddy-l4](https://github.com/mholt/caddy-l4) - Layer 4 proxy plugin for Caddy.

[xcaddy](https://github.com/caddyserver/xcaddy) - Tool for building custom Caddy binaries.
