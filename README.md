# yosys-package

Prebuilt [Yosys](https://github.com/YosysHQ/yosys) binaries. This repo does not contain the synthesizer sources.

The build workflow checks out an upstream tag, compiles Yosys on `ubuntu-24.04`, and attaches `yosys-ubuntu-24.04.tar.gz` to a release of the same name. The archive is a CMake prefix install (`bin/`, `share/yosys/`, …). [`daxzio/setup-yosys`](https://github.com/daxzio/setup-yosys) downloads that asset and adds `bin` to `PATH`. A workflow that uses the action does not compile Yosys.

The binary is licensed the same way as [YosysHQ/yosys](https://github.com/YosysHQ/yosys) (ISC-style / see upstream).

## Publish a version

Actions → Build → Run workflow.

- `tag` is the **package release name** (for example `0.71`).
- `ref` is the upstream git ref to build. Leave empty to use `v<tag>` when that tag exists on [YosysHQ/yosys](https://github.com/YosysHQ/yosys).

The asset URL is:

```text
https://github.com/daxzio/yosys-package/releases/download/<tag>/yosys-ubuntu-24.04.tar.gz
```