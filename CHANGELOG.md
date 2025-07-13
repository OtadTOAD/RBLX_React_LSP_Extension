# Change Log

All notable changes to the "rblx-react-lsp" extension will be documented in this file.

Check [Keep a Changelog](http://keepachangelog.com/) for recommendations on how to structure this file.

## [Unreleased]

- Added command for download API dump.
- Added auto complete suggestions for instance names.
- Added auto complete suggestions for instance properties.

## [0.0.4]

### Added

- Added icon
- Improved README

## [0.0.5]

### Fixed

- Parentheses inside createElement caused the regex to break
- Removed unnecessary server files to reduce size.

## [0.0.6]

### Added

- Includes API cache by default

### Changed

- Added `Programming Languages` category
- Changed command name from `Generate metadata` to `Generate API Metadata`

## [0.0.7]

### Changed

- Fixed issue where this LSP interfered with other LSPs by limiting capabilities to only what’s needed

## [0.1.0]

### Added

- New command for generating API as pretty json for personal use
- Suggestions are now sorted by frequency, length, and lexicographical order.

### Changed

- Using Spawn now during init for async loading
- Now using .bin instead of .json when saving cache

## [0.1.1]

### Added

- Added warning when you open extension for first time.

## [0.1.2]

- Fixed bug where extension stole "language id" so other LSP extensions wouldn't run properly alongside it.
(I had to make this extension run on all files for this, so disable this extension when not in use)