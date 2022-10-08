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