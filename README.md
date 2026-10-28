# Gspace downloads

Gspace helps 1337/42 students keep a small HOME usable and download portable apps
into local goinfre. This repository contains prebuilt downloads; source stays private.

Requires Linux x86_64, glibc 2.35+ (Ubuntu 22.04 or newer), and Node 12.22.9+.
Python and Textual are bundled. No pip, compiler, sudo or Docker is needed.

For a school account with a roaming HOME, install the small launcher **once**:

```sh
curl -fsSL https://gspace-downloads.pages.dev/install.sh | sh
export PATH="$HOME/.local/bin:$PATH"
gspace
```

After that, just run `gspace` on any school PC. Setup adds about 35 KB to your
roaming HOME and configures Bash/Zsh; it uses Node directly, so a broken npm
cache cannot block startup. Curl is needed for the one-time setup. The launcher
finds `$GOINFRE`, `/goinfre/$USER`, or `~/goinfre` automatically on each PC.
Use `gspace --update` to check for runtime updates immediately. Your HOME must
be shared between PCs for this setup to follow you.

The npm entry point remains available with `npx gspace` when npm has a working
cache. Keep that cache in local storage rather than your small roaming HOME.

The Linutil-inspired interface has a sidebar, search, app categories and storage
meters. Use `/` to search, Space to select apps, `d` to download, Enter to open,
and `q` to quit. Existing storage tools remain available in the sidebar.

Official downloads include Zen and qBittorrent AppImages, VS Code, Firefox,
Postman, Discord's official portable installer, and Chromium's development
snapshot. Downloads use HTTPS, pinned SHA-256 checks, parallel ranges, reused
connections and resume. Progress shows the source host and both MB/s and Mbps.
App binaries and new app profiles stay in goinfre. Existing profiles are untouched.
Export important portable-profile data before switching workstations. Removing an
app keeps its profile. Desktop libraries and browser sandbox support still depend
on the workstation; Gspace does not disable browser sandboxes.

Installed apps appear in GNOME Applications with official icons. The current runtime
repairs entries for existing installs when you open Gspace, without downloading
the apps again. Run `gspace --update` to apply it; the existing 0.2.0 launcher
works with this update, with no npm login or reinstall.

**Stay Awake** is available in the sidebar in runtime 0.2.2. Choose **Turn on**
to keep the screen awake: X11 moves the pointer one pixel and back every
15 seconds; GNOME Wayland uses an idle inhibitor. It continues after Gspace
closes. Select **Turn off** or log out to end it. It starts off in new desktop
sessions and needs no sudo or xdotool.

The first launch downloads approximately 17.7 MiB for Gspace itself. Later
launches reuse the verified runtime. Downloads use
[free static Cloudflare Pages](https://gspace-downloads.pages.dev/), with GitHub
Releases as a fallback. CDN routing is automatic; a specific city or download
speed is not guaranteed. Third-party apps download from their publishers.

Builds run locally. This setup uses no R2, Pages Functions, paid CI or rented
server. Included third-party notices are in the runtime's `licenses/` directory.
