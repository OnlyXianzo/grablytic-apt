# TrueStream APT repository (`https://onlyxianzo.github.io/truestream-apt`)

One-time setup (Debian / Ubuntu / Mint):

```bash
curl -fsSL https://onlyxianzo.github.io/truestream-apt/truestream.asc \
  | sudo tee /usr/share/keyrings/truestream.asc > /dev/null
echo "Types: deb
URIs: https://onlyxianzo.github.io/truestream-apt
Suites: stable
Components: main
Signed-By: /usr/share/keyrings/truestream.asc" \
  | sudo tee /etc/apt/sources.list.d/truestream.sources > /dev/null
sudo apt update && sudo apt install truestream
```

After that, every release arrives via `sudo apt upgrade`. Indexes are rebuilt
by [`build-apt.yml`](.github/workflows/build-apt.yml) (signed `InRelease`,
GPG key `2891BE4635EE650EA947F76BE3BEBD9A02F9604A`).
