# Grablytic APT repository (`https://onlyxianzo.github.io/grablytic-apt`)

One-time setup (Debian / Ubuntu / Mint):

```bash
curl -fsSL https://onlyxianzo.github.io/grablytic-apt/grablytic.asc \
  | sudo tee /usr/share/keyrings/grablytic.asc > /dev/null
echo "Types: deb
URIs: https://onlyxianzo.github.io/grablytic-apt
Suites: stable
Components: main
Signed-By: /usr/share/keyrings/grablytic.asc" \
  | sudo tee /etc/apt/sources.list.d/grablytic.sources > /dev/null
sudo apt update && sudo apt install grablytic
```

After that, every release arrives via `sudo apt upgrade`. Indexes are rebuilt
by [`build-apt.yml`](.github/workflows/build-apt.yml) (signed `InRelease`,
GPG key `2891BE4635EE650EA947F76BE3BEBD9A02F9604A`).
