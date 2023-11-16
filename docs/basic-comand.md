---
layout: default
title: Basic Commands
nav_order: 2
---
Basic Commands
---

{: .no_toc }

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
- TOC
{:toc}
</details>

---

### Uninstall a Package

To remove a application compleatly use `apt purge` command.

```console
sudo apt purge --auto-remove packagename
```
---

### System Monitor Tools

To monitor your system you can use [Glances](https://nicolargo.github.io/glances/) to install it:

```console
sudo apt install glances
```

To watch the system performance just hit `glances` on your terminal:

```console
glance
```

---

### Copy | Move | Make File | Rename File | Make Directory

To copy use `cp` command:

```console
cp old_file_name <Space> new_file Name
```

To move use `mv` command:

```console
mv old_file_name <Space> new_file Name
```

To make new file use `touch` command:

```console
touch file_name
```

To rename file use `mv` command:

```console
mv old_file_name <Space> new_file Name
```

To make new directory use `mkdir` command:

```console
mkdir directory_name
```