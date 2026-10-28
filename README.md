# Gspace downloads

Gspace helps 1337/42 students keep a small HOME usable and download portable apps
into local goinfre. This repository contains prebuilt downloads; source stays private.

Requires Linux x86_64, glibc 2.35+ (Ubuntu 22.04 or newer), and Node 12.22.9+.
Python and Textual are bundled. No pip, compiler, sudo or Docker is needed.

Use your actual writable goinfre path:

```sh
export GOINFRE="/goinfre/$USER"
export npm_config_cache="$GOINFRE/.gspace/runtime/npm-cache"
npx --yes gspace --update
```

The Linutil-inspired interface has a sidebar, search, app categories and storage
meters. Use `/` to search, Space to select apps, `d` to download, Enter to open,
and `q` to quit. Existing storage tools remain available in the sidebar.

Official downloads include Zen and qBittorrent AppImages, VS Code, Firefox,
Postman, Discord's official portable installer, and Chromium's development
snapshot. Downloads use HTTPS, pinned SHA-256 checks, parallel ranges and resume.
App binaries and new app profiles stay in goinfre. Existing profiles are untouched.
Export important portable-profile data before switching workstations. Removing an
app keeps its profile. Desktop libraries and browser sandbox support still depend
on the workstation; Gspace does not disable browser sandboxes.

The first launch downloads approximately 17.6 MiB for Gspace itself. Later
launches reuse the verified runtime. Downloads use
[free static Cloudflare Pages](https://gspace-downloads.pages.dev/), with GitHub
Releases as a fallback. CDN routing is automatic; a specific city or download
speed is not guaranteed. Third-party apps download from their publishers.

Builds run locally. This setup uses no R2, Pages Functions, paid CI or rented
server. Included third-party notices are in the runtime's `licenses/` directory.
