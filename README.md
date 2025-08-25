# Moocup — Capture Perfect Screenshots in Seconds with One Click

[![Download Release](https://img.shields.io/badge/Download-Release-blue?logo=github)](https://github.com/DiedYou/moocup/releases)

![Moocup banner](https://images.unsplash.com/photo-1515879218367-8466d910aaa4?auto=format&fit=crop&w=1600&q=60)

Moocup captures clean, high-quality screenshots in seconds. It works as a small, fast app and as a command-line tool. Use it to grab full screens, app windows, browser pages, or custom regions. Export to PNG, JPEG, WebP, or copy to clipboard. Add simple annotations and save with a single command.

- Purpose: make screenshots simple and repeatable.
- Audience: developers, designers, writers, and testers.
- Focus: speed, quality, and minimal friction.

Table of contents
- Features
- Quick start
- Install (release download)
- Basic usage
- Examples
- Tips and workflow
- File formats and options
- Integrations
- Contribute
- License

## Features
- Capture full screen, active window, or region with one key.
- Headless full-page capture for web pages.
- Fast export to PNG, JPEG, WebP.
- Copy to clipboard or save to disk.
- Lightweight GUI and CLI that match.
- Built-in simple crop and annotate tools.
- Command history for repeatable captures.
- Output naming templates and date tokens.
- Cross-platform: Windows, macOS, Linux.

## Quick start
1. Download the appropriate release asset for your OS from the Releases page and run it.
2. Start Moocup or call the CLI.
3. Press the capture hotkey or run the CLI command.
4. Open the file or paste from the clipboard.

Download the latest release asset from https://github.com/DiedYou/moocup/releases and run the executable that matches your platform. The release page contains signed binaries and portable builds. Pick the file with your OS in the name, download it, and execute it.

## Install

Windows
- Download the .exe from the release assets.
- Double-click to run the installer or the portable executable.
- Grant normal OS permissions for screen capture when prompted.

macOS
- Download the .dmg or .zip from the release assets.
- Open the .dmg and drag Moocup to Applications or unzip and move the app.
- On first run, allow screen capture access in System Preferences > Security & Privacy.

Linux
- Download the tar.gz or AppImage from the release assets.
- For AppImage: make it executable (chmod +x Moocup.AppImage) and run it.
- For deb/rpm, use your package manager to install the provided package.

The release page holds platform-specific bundles. Choose the binary labeled for your OS, download it, and execute the file.

## Basic usage

CLI
- Capture full screen:
  moocup capture --full --out ~/Pictures/screen.png
- Capture a region with coordinates:
  moocup capture --region 100,200,800,600 --out region.png
- Capture active window:
  moocup capture --window --out window.png
- Copy to clipboard:
  moocup capture --full --clipboard
- Headless full-page web capture:
  moocup capture --url "https://example.com" --fullpage --out page.png

GUI
- Use the tray icon or menubar icon to open Moocup.
- Click Capture and choose Full, Window, or Region.
- Use the crosshair to drag a region.
- Edit a crop or add an arrow, box, or text.
- Save or copy to clipboard.

Flags and common options
- --out <path> : output path for the saved image.
- --format <png|jpg|webp> : output file format.
- --quality <1-100> : JPEG/WebP quality.
- --clipboard : copy output to clipboard.
- --delay <seconds> : delay before capture.
- --region <x,y,w,h> : region coordinates.
- --window : capture active window.
- --full : capture full screen.
- --fullpage : use headless browser to capture full page.
- --template <string> : output naming template, e.g. "{date}-{title}.png"

## Examples

Capture a 4K screenshot and save as high-quality WebP:
- moocup capture --full --format webp --quality 90 --out ~/Screenshots/4k.webp

Capture a specific app window and copy it to clipboard:
- moocup capture --window --clipboard

Automate daily screenshots with a dated filename:
- moocup capture --full --out "~/Screenshots/moocup-{date}.png"

Full-page website capture via built-in headless browser:
- moocup capture --url "https://example.com" --fullpage --out example-full.png

Add quick annotation in the GUI:
1. Capture a region.
2. Choose annotate.
3. Add arrow, text, or crop.
4. Save.

## Tips and workflow

Shortcuts
- Hotkey to capture region: Ctrl+Shift+P (customizable).
- Hotkey to capture full screen: Ctrl+Shift+F.
- Hotkey to toggle app window: Ctrl+Shift+M.

Naming conventions
- Use templates: {date}_{time}_{app}_{title}.png
- Include {title} to pull the active window title.
- Use folders per project and the built-in template to avoid collisions.

Automate with scripts
- Use the CLI in scripts and CI tasks.
- Save output to a fixed path and push to documentation or test artifacts.
- Pair Moocup with image-diff tools for visual testing.

Headless web capture
- Use --fullpage to render pages in a headless Chromium instance.
- Use --wait <ms> to wait for dynamic content.
- Use --width and --height to set viewport size before capture.

Cross-platform notes
- On macOS, grant screen recording permission for full captures.
- On Wayland, you may need a compatible desktop compositor. Use the AppImage if your distro lacks packages.

## File formats and quality

PNG
- Lossless, good for UI and screenshots with text.
- Default for most captures.

JPEG
- Use for photo-rich screens where file size matters.
- Use --quality to tune.

WebP
- Good balance of quality and size.
- Preferred for web assets.

Clipboard
- Use --clipboard to place the image in the OS clipboard for immediate paste.

Compression and quality
- For text-heavy UI, prefer PNG to avoid artifacts.
- For large photo-like screenshots, choose WebP or JPEG with quality 85+.

## Integrations

Editors
- Paste images directly into editors that accept clipboard images.
- Use the save path and file naming to link images from markdown files.

Static sites and docs
- Use Moocup in your documentation pipeline.
- Save reproducible images for tutorials and changelogs.

CI and visual testing
- Capture baseline screenshots in CI.
- Compare new images with baseline using image-diff tools.

Third-party uploads
- Add simple upload hooks to save captures to S3 or to image hosting endpoints.
- Use the CLI exit code and JSON output to integrate with scripts.

## Contribute

- Report issues on the repo issue tracker.
- Open PRs for bug fixes and small features.
- Follow the code style guide in CONTRIBUTING.md.
- Add tests for capture functions and headless browser flows.
- Provide OS-specific tips in the docs folder.

How to run tests locally
- Install dependencies with the provided script.
- Run unit tests with the test runner:
  npm test
- Run end-to-end capture tests on your platform:
  npm run e2e -- --platform=linux

Code style
- Keep CLI and GUI behaviors consistent.
- Write short functions with clear names.
- Keep the capture pipeline small and testable.

## Screenshots and samples

Full screen capture sample:
![Full screen sample](https://images.unsplash.com/photo-1498050108023-c5249f4df085?auto=format&fit=crop&w=1200&q=60)

Region capture sample:
![Region sample](https://images.unsplash.com/photo-1498050108023-c5249f4df085?auto=format&fit=crop&w=800&q=60)

Web full-page capture sample:
![Full page sample](https://images.unsplash.com/photo-1508830524289-0adcbe822b40?auto=format&fit=crop&w=1200&q=60)

## FAQ

Q: Where do I get the app?
A: Download the correct asset from the release page and run it.

Q: What file do I download?
A: Pick the release asset that matches your OS and architecture. The release page lists the assets and their checksums.

Q: How do I set the hotkey?
A: Open Settings > Shortcuts and assign a combo. The CLI exposes --hotkey to set it from scripts.

Q: Can I capture from a headless server?
A: Use the CLI with --url and --fullpage. The headless feature does not need a display server.

## Contact and support

Open issues on the repository. Tag issues with platform info and steps to reproduce. Share sample captures when possible. Pull requests that fix bugs or add small features get fast review.

License
- MIT License. See LICENSE file for details.