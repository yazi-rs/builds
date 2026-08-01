# Yazi binary builds

This repository hosts the official Yazi APT repository at <https://yazi-rs.github.io/builds/>.

## Install stable

```sh
curl -fsSL https://yazi-rs.github.io/builds/yazi-keyring.gpg | sudo tee /usr/share/keyrings/yazi-keyring.gpg >/dev/null
echo 'deb [signed-by=/usr/share/keyrings/yazi-keyring.gpg] https://yazi-rs.github.io/builds/ stable main' | sudo tee /etc/apt/sources.list.d/yazi.list >/dev/null
sudo apt update && sudo apt install yazi
```

## Install nightly

```sh
curl -fsSL https://yazi-rs.github.io/builds/yazi-keyring.gpg | sudo tee /usr/share/keyrings/yazi-keyring.gpg >/dev/null
echo 'deb [signed-by=/usr/share/keyrings/yazi-keyring.gpg] https://yazi-rs.github.io/builds/ nightly main' | sudo tee /etc/apt/sources.list.d/yazi.list >/dev/null
sudo apt update && sudo apt install yazi
```

The nightly suite is marked as `NotAutomatic`, so it does not automatically
replace a stable installation when both sources are configured.

## Security

Packages are authenticated by the Ed25519 key in [`yazi-keyring.gpg`](yazi-keyring.gpg), fingerprint:

```text
B77B 412E 5B65 3539 B786  95DC 9243 8579 6056 0E6C
```
