# Workspace

A docker-based workspace which helps the developer to focus on what they are doing best: coding!

The idea behind is inspired from a wide-range of repositories and primarily target to Magento 2 Developers.

Many thanks to:

[weprovide/valet-plus](https://github.com/weprovide/valet-plus/)
[meanbee/docker-magento2](https://github.com/meanbee/docker-magento2)
[magento/magento-cloud-docker](https://github.com/magento/magento-cloud-docker)


# Prerequisites

1. Docker CE/EE & docker-compose
2. Composer

# Installation

This is a CLI application which recommended to install by Composer.

```bash
$ composer global require nntoan/workspace
```

# Usage

### Builds

To use the workspace, you will need to build your own docker container by using the following commands.

The `Dockerfile` location listed in this repository wiki.

Let's say we are building a workspace for Magento 2.3.x, we can use these:

```bash
$ ws build:php --version=7.2

$ ws build:nginx --version=1.13

$ ws build:varnish

$ ws build:mysql --version=5.7

## Optional

$ ws build:redis --version=3.2

$ ws build:elasticsearch --version=5.2

$ ws build:rabbitmq --version=3.5
```

or we can use a pre-defined command to install of above services

```bash
ws build:magento2
```

after all build processes finished, you will see the whole repository contains `Dockerfile` pulled under `~/.workspace/Containers`.

### Configurations

All "WS" configs can be found under `~/.workspace/`. This tool provides the most flexible way to handle your own workspace

to work with multiple projects at the same time by just adjust the YAML and ENV files.

### Basis stuff

In daily basis tasks, as same as docker-compose, what we do:

```bash
$ ws start

$ ws restart

$ ws reload

$ ws stop
```

it's a **MUST** to run `ws reload` after you change anything with your YAML or ENV files.

*...to be continued*
