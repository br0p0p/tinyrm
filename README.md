# `tinyrm`

> A tiny CLI tool to remove files and directories

**This is a fork of [`premove`](https://github.com/lukeed/premove). Credit goes to that project for this CLI. This fork exists because Node v14.14 introduced `fs.rm()` and `fs.rmSync()`, providing the necessary deletion functionality out of the box. `premove` supports Node v6, which lacks these methods, so it implements them in userland. If you use Node v14.14 or later, the v6-compatible code is unnecessary.**

`tinyrm` is a cross-platform CLI tool for recursively removing files and directories. It does not export a Node API; it is a simple CLI wrapper around Node's `fs.rmSync`.

For programmatic deletion, use `fs.rm()` / `fs.rmSync()` or [`premove`](https://github.com/lukeed/premove).

## Features

- Supports Node v14.14 or later
- By default, `tinyrm` refuses to delete:
  - the [home directory](https://nodejs.org/api/os.html#os_os_homedir)
  - the system root (`/`, `C:\\`, etc.)
  - items outside the `--cwd` path

## Install

```sh
# Globally
npm i -g tinyrm

# Locally
npm add -D tinyrm
```
