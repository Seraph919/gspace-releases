# Gspace downloads

Gspace helps 1337/42 students move selected caches and reproducible developer data
from roaming HOME to local goinfre. This repository contains prebuilt downloads.
The source repository is private.

Requires Linux x86_64 with glibc 2.35+ (Ubuntu 22.04 or newer) and Node 12.22.9+.
Python and Textual are bundled. No pip, compiler, sudo or Docker is needed.

If your local storage is `/goinfre/$USER`, run:

```sh
export GOINFRE="/goinfre/$USER"
export npm_config_cache="$GOINFRE/.gspace/runtime/npm-cache"
npx gspace
```

Use your actual writable goinfre path if different. Append `status --json`,
`analyze`, or `doctor` to run a command instead of the interface. The
[public npm launcher](https://www.npmjs.com/package/gspace) needs no npm account
to install or run.

First launch downloads a 10.8 MiB runtime, verifies its checksums and unpacks it
inside goinfre. Later launches reuse it. Updates are checked once per day;
`--update` forces a check. If an update fails, the existing verified runtime is
used. Actual first-download time depends on the workstation's connection.

Use arrows and Enter to navigate, Space to select items, Escape to go back, and
`q` to quit. Close affected applications before moving or cleaning their data.
The interface asks for confirmation before mutations. Local goinfre is not a
backup: when switching workstations, cached/reproducible data may need rebuilding
or reinstalling.

Builds run locally and downloads use GitHub Releases. This setup does not use
Cloudflare R2, paid CI or a cloud server. Included third-party license notices are
inside the runtime archive's `licenses/` directory.
