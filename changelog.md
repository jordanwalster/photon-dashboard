# Changelog

All notable changes to this project will be documented in this file.

## [v0.0.8] - 2025-01-30

### Fixed
- Some tags elements attempting to load when `TAGS_ENABLED` set to false.

## [v0.0.7] - 2025-01-29

### Added
- Empty trash button.
- Screenshot counter to sidebar.
- Trash counter to sidebar.

### Fixed
- Expanded tags view persisting between page refreshes.
- Image names displaying the trash hash value when on trash page.

## [v0.0.6] - 2025-01-29

### Changed
- Changelog URL set to Github changelog.md.
- Deleted images hash separator.

### Fixed
- Pagination layout issues [#10](https://git.jrdn.dev/jordanwalster/photon-dashboard/issues/10).

## [v0.0.5] - 2025-01-29

### Added
- Trash functionality to untagged images.
- Permanent deletion functionality.
- Configurable column count from dropdown.

### Changed
- Padding at the bottom of the page is reduced to 35px from 50px.

## [v0.0.4] - 2025-01-28

### Added

- Update compose file to use bind mount.
- Delete tag button.
- Image tag pagination.
- Tagged Screenshots pages.
- Override for default page limit.

### Fixed

- Bug where selected tags from a previous image wouldn't clear correctly after modal close.

## [v0.0.3] - 2025-01-27

### Added

- Filter buttons for mimetype.
- Tag attachment counter.
- Image tagging.
- Support for tag creation.


## [v0.0.2] - 2025-01-26

### Added

- Gravatar profile pictures.
- Download image function.
- Flags for disabling incomplete functions (search, tagging).

## [v0.0.1] - 2025-01-25

### Added

- Image format labels to dashboard.
- Rename image function.
- Copy link to clipboard function.
- A changelog to document changes.
