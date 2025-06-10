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