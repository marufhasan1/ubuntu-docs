---
layout: default
title: Basic Commands
nav_order: 2
---
Basic Commands
---

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

### Uninstall a Package

To remove a application compleatly use `apt purge` command.

```console
sudo apt purge --auto-remove packagename
```
---

### Ubuntu System Monitor Tools

To monitor your system you can use [Glances](https://nicolargo.github.io/glances/) to install it:

```console
apt install glances
```

To watch the system performance just hit `glances` on your terminal:

```console
glance
```

