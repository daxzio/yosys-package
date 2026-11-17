# yosys-package

Prebuilt [Yosys](https://github.com/YosysHQ/yosys) binaries. This repo does not contain the synthesizer sources.

The build workflow checks out an upstream tag, compiles Yosys on **ubuntu-24.04** and **ubuntu-26.04**, and attaches both tarballs to one release:

- `yosys-ubuntu-26.04.tar.gz` — use on `ubuntu-26.04` / `ubuntu-latest` (while latest is 26.04)
- `yosys-ubuntu-24.04.tar.gz` — use on `ubuntu-24.04`

[`daxzio/setup-yosys`](https://github.com/daxzio/setup-yosys) picks the right asset automatically. A workflow that uses the action does not compile Yosys.

The binary is licensed the same way as [YosysHQ/yosys](https://github.com/YosysHQ/yosys) (ISC-style / see upstream).

## Publish a version

Actions → Build → Run workflow.

- `tag` is the **package release name** (for example `0.71`).
- `ref` is the upstream git ref to build. Leave empty to use `v<tag>` when that tag exists on [YosysHQ/yosys](https://github.com/YosysHQ/yosys).
- `targets` — build both images (`all`), or only `24.04` or `26.04`.

Asset URLs:

```text
https://github.com/daxzio/yosys-package/releases/download/<tag>/yosys-ubuntu-26.04.tar.gz
https://github.com/daxzio/yosys-package/releases/download/<tag>/yosys-ubuntu-24.04.tar.gz
```