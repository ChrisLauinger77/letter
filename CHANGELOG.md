# Changelog

All notable changes to Letter are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project follows [Semantic Versioning](https://semver.org/).

How we maintain it:

- During development, add bullets under **[Unreleased]**.
- On each release (rc or stable), rename that section to the version + date, and
  copy a short summary into `data/io.github.stalvatero.Letter.metainfo.xml.in.in`
  (`<releases>`) and the GitHub Release notes.
- Prefer user-visible changes (features, fixes, translations). Skip internal
  refactors unless they affect behaviour.

## [Unreleased]

### Fixed

- Meeting invitation times use the event timezone (no more +2h shift in Rome).
- Invitation UI strings are included in gettext again (Italian/German).
- Accept/Decline update the UI and move the invite to Trash immediately; calendar
  sync continues in the background instead of blocking for many seconds.

## [1.0.0-rc.1] - 2026-09-08

### Added

- First Flatpak bundle for GitHub Releases (GNOME Platform 50; not on Flathub yet).
- Undo toast for archive, move, and trash.
- CI validation on Fedora 44.

### Changed

- Startup always opens Inbox for the last selected account (folder selection is
  no longer restored).
- Cache-first folder trees and message lists for faster account switching.

### Fixed

- Folder-tree disk cache writes after the cache directory already exists.
- Thread focus after archiving a message inside a conversation.
- Localized well-known folder names (Drafts, Sent, …) in the UI locale.

[Unreleased]: https://github.com/stalvatero/letter/compare/v1.0.0-rc.1...HEAD
[1.0.0-rc.1]: https://github.com/stalvatero/letter/releases/tag/v1.0.0-rc.1
