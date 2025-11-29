# void-hybrid

`void-hybrid` is an helper script for managing Void Linux packages.  
It automates common tasks like searching, installing, building from source, and maintaining `void-packages`.

## Features

- Search Void Linux repositories (`xbps-query`)
- Install packages with fallback to building from source (`xbps-src`)
- Update the system and installed packages
- Create new package templates with `xnew`
- Setup `void-packages` automatically (clone + binary-bootstrap)
- Cleanup orphaned packages and cache
- Supports non-interactive mode for scripts or automation

## Installation

Clone the repository or copy the script:

```bash
git clone https://github.com/USERNAME/void-hybrid.git
cd void-hybrid
```
Move to /usr/bin

```bash
sudo mv void /usr/bin/
```
Make the script executable so it can run as a program:

```bash
sudo chmod +x /usr/bin/void
```

Now you can run it from anywhere:

```bash
void [options] <package|command>
```
## Commands:
```bash
  <name>                Search (xbps-query -Rs <name>) if single non-option arg
  -S [--install] ...    Try xbps-install; on failure automatically attempt xbps-src fallback
  -Su                   Run xbps-install -Su (system upgrade)
  -R <pkg>...           Remove packages (xbps-remove)
  --src <pkg>           Force build and install with xbps-src
  --new <pkg>           Create a new template (xnew)
  -V, --vpsync          Update local void-packages (git pull)
  -Oo                   Cleanup orphans and cache
  --setup               Setup void-packages (clone + binary-bootstrap)
  --yes, -y             Non-interactive / assume yes
  --verbose             More logs
  -h|--help             Show this help

```

## Notes

- `void-hybrid` minimizes manual steps for managing Void Linux packages.
- Can auto-clone `void-packages` if missing.
- Can run `binary-bootstrap`, create templates with `xnew`, and build packages if binary install fails.
- Use `--yes` for non-interactive mode; use with caution.

## License

MIT License — freely use, modify, and redistribute with attribution.
