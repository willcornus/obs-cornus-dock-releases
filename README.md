# Cornus Dock for OBS Studio

Cornus Dock is an OBS Studio plugin that adds a dedicated dock for **Kick chat** inside the OBS interface.

It uses OBS's built-in browser dock runtime through the public `obs-browser` panel API (`QCef`, `QCefWidget`), so the chat runs directly inside OBS without requiring a separate browser window.

This repository is used to publish **public binary releases** of the plugin.

## What it does

Cornus Dock lets you:

- open **Kick popout chat** directly in an OBS dock
- configure either a **Kick channel** or a **custom chat URL**
- use OBS browser popup settings to control how external links are handled
- keep the chat available inside your normal OBS workspace

When the external links option is enabled, links are handled through OBS popup behavior so they can open outside the dock in the system default browser.

When that option is disabled, the dock behaves like a regular OBS browser dock.

## How it works

Cornus Dock is intentionally lightweight.

Instead of embedding its own Qt WebEngine browser, it uses the browser runtime already provided by OBS through the `obs-browser` module. The plugin dynamically loads the OBS browser panel API at runtime and creates its dock from that.

This keeps the plugin small and aligned with how OBS browser docks already work.

## Download

Open the [Releases](../../releases) page and download the latest version:

- **Windows Installer (`.exe`)** — recommended for most users
- **Windows ZIP (`.zip`)** — manual installation

## Installation

### Windows Installer
1. Download the latest `.exe` file from the Releases page.
2. Run the installer.
3. Start OBS Studio, or restart it if it is already running.

### Windows ZIP
1. Download the latest `.zip` file from the Releases page.
2. Extract it into your OBS Studio plugins directory.
3. Start OBS Studio, or restart it if it is already running.

## Configuration

After installation, open the plugin settings in OBS and configure one of these:

- a **Kick channel name**
- a **custom URL**

If a custom URL is set, it is used directly.

If the custom URL is empty, the plugin builds the Kick popout chat URL from the configured channel.

## Runtime requirement

Your OBS installation must include the **`obs-browser`** module, because Cornus Dock depends on the OBS browser dock runtime and loads its panel API dynamically at runtime.

## Installed location

On Windows, the plugin is typically installed to:

`C:\ProgramData\obs-studio\plugins\obs-cornus-dock`

## Compatibility

- **Windows x64**
- **OBS Studio** with browser dock support

Exact compatibility may vary by release.

## Issues and feedback

If you find a bug or want to request a feature, please use the main project repository.

## Notes

This repository is for **binary releases only**.

Source code and development are maintained separately in the main project repository.
