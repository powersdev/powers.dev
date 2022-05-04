---
layout: page
title: Local
---

[Github Repo](https://github.com/powersdev/local)

Automated local development environments.

## Contents

The most important files and directories are listed below.

```shell
# Landofiles
.lando.base.yml
.lando.yml

# Binaries
bin/

# Configuration Files
config/

# Code Quality
composer.json
phpcs-compat.xml
phpcs.xml
```

### Landofiles

There are two landofiles:

```
.lando.base.yml	# Base Configuration
.lando.yml		# Site Configuration
```

Only the `.lando.yml` file is intended to be edited by the user. The other file includes default values that rarely need changing.

The files are only split to streamline the new site setup process for users other than myself who don't need to see all that.

Ultimately, one needs to declare the location of the site files repo, the wpengine environment name, and the names of the ssh keys used for each. Upon typing `lando start`, the rest of the setup process is automated.

### Binaries

The `bin` folder contains a collection of python and bash scripts. The original project was a couple of bash scripts, but it has since evolved. (I'm not terribly happy with the outcome of the python rewrite, so I'm now looking at [hush](https://hush-shell.github.io/) as a potential replacement.)

I could go through each script, but that's boring. Here's an overview of what the collection can do:

1. Set up tooling inside the container, such as node and python
2. Download and install the latest version of WordPress
3. Pull files and data from the production environment via `ssh` and `rsync`
4. Import Vaultpress data (for VIP sites)
5. Set up themes by installing npm dependencies and running build tools
6. Perform automatic search and replace on regular sites and multisite network


## Summary

These tools allow the user to create a nearly exact duplicate of a production site in 10 minutes or less.

The process of building this tool has brought me great joy. There is nothing better than the excitement of my coworkers when it "just works". 
