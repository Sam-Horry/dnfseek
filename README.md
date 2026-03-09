# dnfseek

A TUI (terminal user interface) package browser for Fedora, inspired by [pacseek](https://github.com/moson-mo/pacseek) from Arch Linux. This is a fork of [dnfseek](https://github.com/OmarHesham2356/dnfseek), with improvements made to performance, caching of package lists, and reductions in unnecessary calls to Fedora mirrors.

It uses [fzf](https://github.com/junegunn/fzf) to provide a searchable, interactive interface for browsing, installing, removing, and updating packages via `dnf`.

## ✨ Features

- 🔎 Search all packages or show only installed ones
- ✅ Installed packages are highlighted in green with a checkmark
- 📜 Live preview of package information (`dnf info`)
- 📦 Context-aware actions (Install, Reinstall, Remove, Update)
- 🧩 View package dependencies
- ↩️ "Back" functionality via `Esc` or `Ctrl-C`
- 🆙 Upgrade all packages from the main menu
- 🔄 Automatic caching (refreshes every 24 hours)
- ⚡ Fast and lightweight (Bash + fzf)

## 📸 Screenshot

![Demo](demo.gif)

## 🛠️ Requirements

- **Fedora** (tested with `dnf` and `dnf5`)
- `fzf`
- `dnf`

Install `fzf`:

```bash
sudo dnf install fzf
```

## 🚀 Usage

### Quick Start

Clone the repo and run:

```bash
git clone https://github.com/Sam-Horry/dnfseek.git
cd dnfseek
chmod +x dnfseek
./dnfseek
```

### Global Installation

To run `dnfseek` from anywhere:

```bash
sudo cp dnfseek /usr/local/bin/dnfseek
```

And then just run:

```bash
dnfseek
```

## ⌨️ Controls

| Key | Action |
|-----|--------|
| `↑`/`↓` | Navigate lists |
| `Enter` | Select package or action |
| `Esc` / `Ctrl-C` | Go back / Exit |
| `Type` | Filter package list |

## 📁 Files & Cache

- **Script:** `/usr/local/bin/dnfseek` (if installed)
- **Cache Directory:** `~/.cache/dnfseek/`
- **Installed List:** `~/.cache/dnfseek/installed`
- **Available List:** `~/.cache/dnfseek/available`

The package cache is automatically updated if it's older than 24 hours. You can also manually refresh it from the main menu.

A cache is also made for individual package info to reduce the number of times that `dnf info` is run.
