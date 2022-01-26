<div align="center">
  <h1>
    Standardnotes-Standalone
    <br />
  </h1>
  Multi-arch Standard Notes Syncing Infrastructure
  <br />
  <br />
</div>

## Note
This repository only creates multi-arch images for standardnotes from the standardnotes repositories using Github Actions.
Everything is the same as [standardnotes/standalone](https://github.com/standardnotes/standalone), except the docker-compose file images.

![Auth](https://github.com/TheMardy/standardnotes-standalone/actions/workflows/auth.yml/badge.svg)
![Api-Gateway](https://github.com/TheMardy/standardnotes-standalone/actions/workflows/api-gateway.yml/badge.svg)
![Syncing-Server-JS](https://github.com/TheMardy/standardnotes-standalone/actions/workflows/syncing-server-js.yml/badge.svg)

## 🐳 Supported platforms

| Platform  | Tested |
| --- | --- |
| `linux/amd64` | ✓ |
| `linux/arm/v6` | - |
| `linux/arm/v7` | ✓ |
| `linux/arm64` | ✓ |
| `linux/ppc64le` | - |
| `linux/s390x` | - |

Note: You might need to choose a different mariadb image if you use `s390x`, `ppc64le` or `arm/v6`.


## Latest Version check
|   | Standardnotes | Multi-Arch |
|---|---|---|
| Auth | ![GitHub tag (latest by date)](https://img.shields.io/github/v/tag/standardnotes/auth) | ![TheMardy](https://img.shields.io/docker/v/themardy/sn-auth) ![Docker Pulls](https://img.shields.io/docker/pulls/themardy/sn-auth) | 
| Api-Gateway | ![GitHub tag (latest by date)](https://img.shields.io/github/v/tag/standardnotes/api-gateway) | ![TheMardy](https://img.shields.io/docker/v/themardy/sn-api-gateway) ![Docker Pulls](https://img.shields.io/docker/pulls/themardy/sn-api-gateway) |  
| Syncing-Server-JS | ![GitHub tag (latest by date)](https://img.shields.io/github/v/tag/standardnotes/syncing-server-js) | ![TheMardy](https://img.shields.io/docker/v/themardy/sn-syncing-server-js) ![Docker Pulls](https://img.shields.io/docker/pulls/themardy/sn-syncing-server-js) |  


## Installation

#### 1. Clone this repository
```bash
git clone https://github.com/themardy/standardnotes-standalone.git && cd standardnotes-standalone
```
#### 2. Initialize default configuration files by typing:
```bash
./server.sh setup
```
#### 3. Customize your configuration
There are 4 environment variables that need to be filled in with generated secret keys:

`AUTH_JWT_SECRET` in the .env file
`JWT_SECRET`, `LEGACY_JWT_SECRET` and `ENCRYPTION_SERVER_KEY` in the docker/auth.env file
You can generate values for them by using:
```bash
openssl rand -hex 32
```
#### 4. Run:
```bash
./server.sh start
```
