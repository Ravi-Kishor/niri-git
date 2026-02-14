# niri-git (Prebuilt Arch Package)

Prebuilt Arch Linux package for **niri**, built automatically from upstream Git and published via GitHub Releases.

No AUR.  
No pacman repo.  
No manual builds.

---

## 📦 Package

| Package   | Description                                  |
|------------|----------------------------------------------|
| niri-git  | Scrollable-tiling Wayland compositor (git build) |

Builds include:

- x86_64_v3 optimized builds (preferred)
- Built from latest upstream Git
- LTO enabled
- Stripped binaries
- Automatically released via GitHub Actions (every 12h)

---

# 🚀 Install / Update

```bash
curl -fLO https://raw.githubusercontent.com/Ravi-Kishor/niri-git/main/update-niri
chmod +x update-niri
sudo mv update-niri /usr/local/bin/update-niri
update-niri
```

---

## 🧠 What the updater does

- Checks installed version via pacman
- Fetches latest GitHub release
- Prefers x86_64_v3 build
- Falls back to generic x86_64
- Downloads using aria2 (multi-connection)
- Installs automatically

Interactive mode:
- Update only if newer
- Force reinstall

---

## 🏗 Build Info

- Built inside official Arch Linux container
- Built from upstream `main` branch
- LTO enabled
- Stripped binaries
- x86_64_v3 builds include:
  - AVX2
  - BMI1/BMI2
  - FMA

Provides:
```
niri
wayland-compositor
```

Conflicts with:
```
niri
niri-bin
```

---

## ⚠ Requirements

Arch Linux only.

Requires:

- pacman
- curl
- jq
- aria2
- sudo

---

## ⚠ CPU Compatibility

x86_64_v3 builds require a CPU with AVX2 support.

Check with:

```bash
lscpu | grep avx2
```

If unsupported, use the generic x86_64 build.
