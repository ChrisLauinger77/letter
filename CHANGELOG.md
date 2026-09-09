# Changelog

All notable changes to Letter are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project follows [Semantic Versioning](https://semver.org/).

How we maintain it:

- During development, add bullets under **[Unreleased]**.
- On each release (rc or stable), rename that section to the version + date, and
  copy a short summary into `data/io.github.stalvatero.Letter.metainfo.xml.in.in`
  (`<releases>`, leave msgstr empty in po files — keep release notes in English)
  and the GitHub Release notes.
- Prefer user-visible changes (features, fixes, translations). Skip internal
  refactors unless they affect behaviour.

## [Unreleased]

## [1.0.0-rc.2] - 2026-09-09

### Added

- Compact “Important message” badge for high-priority mail (sender Importance);
  list/thread icons only — no user toggle on Microsoft accounts.
- Localized search operators via gettext (`contains:` / `from:` / `to:` plus
  Italian `contiene:` / `da:` / `a:` and German `enthält:` / `von:` / `an:`);
  English operators always work.

### Changed

- AppStream release notes stay English in translations (leave msgstr empty) so
  translators are not asked to update them on every release.

### Fixed

- Microsoft 365 bookmarks map to Outlook Flag (follow-up), not High Importance;
  flag push uses Camel `folder.synchronize`, and marking read no longer wipes a
  remote Flag.
- Meeting invitation times use the event timezone (no more +2h shift in Rome).
- Invitation UI strings are included in gettext again.
- Accept/Decline update the UI and move the invite to Trash immediately; calendar
  sync continues in the background.

### Translations

- German UI completed (Christian Lauinger), including Gmail Labels, well-known
  folder names, undo toasts, and cache-loading strings.

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

[Unreleased]: https://github.com/stalvatero/letter/compare/v1.0.0-rc.2...HEAD
[1.0.0-rc.2]: https://github.com/stalvatero/letter/compare/v1.0.0-rc.1...v1.0.0-rc.2
[1.0.0-rc.1]: https://github.com/stalvatero/letter/releases/tag/v1.0.0-rc.1
