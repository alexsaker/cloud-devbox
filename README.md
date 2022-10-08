# Cloud Devbox

## Overview

The idea behind this repository is to be able to manage devboxes for infrastructure as code projects
using the Nx framework.

## Quickstart

```bash
npm install
```

## Build All Devboxes

```bash
npx lerna run build docker:build
```

## Build Azure Devbox

```bash
npx lerna run build docker:build:devbox-azure
```

## Build GCP Devbox

```bash
npx lerna run build docker:build:devbox-gcp
```

## Build AWS Devbox

```bash
npx lerna run build docker:build:devbox-aws
```

## Semantic Versionning

This project uses conventional commits conventions. 
Those conventions allow for  automatic CHANGELOG.md file generation.
The following command will:
 - ask for the new versions of the touched packages
 - update package.json accordingly
 - tag repository accordingly
 - write changes to CHANGELOG.md file

```bash
npm run version
```