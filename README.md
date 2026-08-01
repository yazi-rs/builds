# Yazi binary builds

This repository hosts the official Yazi APT repository at
<https://yazi-rs.github.io/builds/>.

## Install stable

```sh
curl -fsSL https://yazi-rs.github.io/builds/yazi-keyring.gpg |
  sudo tee /usr/share/keyrings/yazi-keyring.gpg >/dev/null

sudo tee /etc/apt/sources.list.d/yazi.sources >/dev/null <<'EOF'
Types: deb
URIs: https://yazi-rs.github.io/builds/
Suites: stable
Components: main
Signed-By: /usr/share/keyrings/yazi-keyring.gpg
EOF

sudo apt update
sudo apt install yazi
```

## Install nightly

Add `nightly` alongside `stable` in `/etc/apt/sources.list.d/yazi.sources`:

```text
Suites: stable nightly
```

Then install it explicitly:

```sh
sudo apt update
sudo apt install -t nightly yazi
```

The nightly suite is marked as `NotAutomatic`, so it does not replace a
stable installation unless explicitly selected.

## Security

Packages are authenticated by the Ed25519 key in
[`yazi-keyring.gpg`](yazi-keyring.gpg), fingerprint:

```text
B77B 412E 5B65 3539 B786  95DC 9243 8579 6056 0E6C
```
