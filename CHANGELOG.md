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
- Added example .gif to showcase how LSP works.

## [0.2.0]

### Added

- Added auto complete for instance events(For some reason roblox api dump lacks some events, I have no idea how to fix that like .Activated for UI elements).

### Removed

- Removed '{' character triggering auto complete menu automatically, it was annoying when using .createElement method.

## [0.2.1]

### Fixed

- Accidentally removed superclass merging it's properties/events in version 0.2.0 and put it back.

## [0.2.2]

### Changed

- Updated ReadMe to include new feature.
- Added 'Keywords' for easier search of the extension.

## [0.2.3]

### Fixed

- Changed brackets('{}', '[]') being solved using regex and instead they now use same method as normal parentheses. This caused issues with stacking elements.

### Added

- LSP now supports ability to define macros for .createElement instead of having to directly use it from React variable.
    `local e = React.createElement` did not work and was ignored by LSP before.

### Changed

- Fixed binary bloat a bit and made server bit smaller.

## [0.3.0]

### Fixed

- Using 'genMetadata' command doing nothing.
- Assignment checks failing when seeing ==/~=/<=/>=
- Nested groups(Brackets like { {} }) not being properly accounted for and messing up context checks.
    - Will now only give you suggestions in valid bracket.
- Brackets not being checked properly which detected invalid patterns such as ["String"].

### Added

- Now will provide suggestions for [React.Change.Property] pattern.
- Feedback messages when using extension commands.

### Changed

- Now downloads API dump from 'clientsettingscdn.roblox.com' instead of 'setup.rbxcdn.com'(Will fallback to this if first one fails)
    - This should provide more up to date data.
- Now suggestions provided by this extension will have much higher priority.
- Now will no longer take capitalization into account when checking for React package(So you can have .react for example)

## [0.3.2]

### Changed

- Added some things to .vscodeignore

## [0.3.3]

### Added

- Version checking to cache.
    - Will now provide user with notification to update their cache if it's stale.

### Changed

- Changed README.md and package.json.