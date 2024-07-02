# `tinyrm`

> A tiny CLI to replace `rimraf`, `premove`, or similar tools.

**This is a fork of [`premove`](https://github.com/lukeed/premove) and all credit goes to that project for this CLI. The reason for this fork is because Node v14.14 introduced `fs.rm()` and `fs.rmSync()` which provide the necessary deletion functionality out of the box. `premove` aims to support Node v6 which does not have these methods so `premove` implements them in userland. If you are using Node v14.14 or greater, the v6-compatibile code is not necessary.**

This is a cross-platform CLI tool to recursively remove files and directories. There is no Node API exported as this is just an extremely simple CLI wrapper around Node's `fs.rmSync`.

If you need programmatic deletion, use `fs.rm()` / `fs.rmSync()` or [`premove`](https://github.com/lukeed/premove).

## Features

- Supports Node v14.14 or greater
- By default premove refuses to delete:
  - the [`os.homedir`](https://nodejs.org/api/os.html#os_os_homedir)
  - the system root (`/`, `C:\\`, etc)
  - items not contained by `--cwd` path

## Install

```sh
# Globally
npm i -g tinyrm

# Locally
npm add -D tinyrm
```
