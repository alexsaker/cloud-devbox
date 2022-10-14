# Cloud Devbox

## Overview

The idea behind this repository is to be able to manage devboxes for infrastructure as code projects
using the Nx framework.

## Quickstart

```bash
npm install
```

## Global commands

### Build All Devboxes

```bash
npx lerna run docker:build
```
### Commit Code

```bash
npm run commit
```

### Semantic Versionning

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

## Azure Devbox

### Basic Devbox

#### Build Image

```bash
npx lerna run docker:build --scope basic-devbox-azure
```

#### Run Image

```bash
npx lerna run docker:run --scope basic-devbox-azure
```


## GCP Devbox

### Basic Devbox

#### Build Image

```bash
npx lerna run docker:build --scope basic-devbox-gcp
```

#### Run Image

```bash
npx lerna run docker:run --scope basic-devbox-gcp
```


## AWS Devbox

### Basic Devbox

#### Build Image

```bash
npx lerna run docker:build --scope basic-devbox-aws
```

#### Run Image

```bash
npx lerna run docker:run --scope basic-devbox-aws
```
