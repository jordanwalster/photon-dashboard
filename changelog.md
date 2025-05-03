# Changelog

All notable changes to this project will be documented in this file.

## [v0.1.3] - 2025-05-03

### Added
- Upload button for uploading via web dashboard.

### Changed
- Column dropdown is now a button that switches between options.
- Some old icons have been switched to FontAwesome icons.
- Sidebar remaining open flag is now set by a cookie instead of a session token.

### Fixed
- Page refresh loop when changing column count.
- Scrollbar failing to show after page content changes.
- Bug where images with capitalised file extensions do not appear in the grid.
- Unable to use multi select actions on images with spaces in their names.

### Removed
- `TAGS_ENABLED`, `SEARCH_ENABLED` and `TRASH_ENABLED` environment variables, these are now permanently enabled.

## [v0.1.2] - 2025-04-29

> [!WARNING]  
> This introduces a breaking change that requires the latest version of the photon-worker container image.

### Added
- Image compression worker function, decreasing page load times.

## [v0.1.1] - 2025-04-28

### Fixed
- Columns not updating when selected in dropdown.
- Icons missing from context menu on search page.

### Changed
- Version numbers are now taken from container image.

## [v0.1.0] - 2025-04-27

### Fixed
- Sharing URL Scheme set to `https` regardless of setting in environment variables.
- Search not clearing the first two characters after emptying search field.
- Error handing for existing tag names.
- Double click bug on modals.
- Permanently deleting images did not remove from db
- Pagination on tagged pages showed in the corner.

### Changed
- Upgraded to PHP 8.
- Database engine now using MySQL.
- Mandatory setting for admin url removed.

### Added
- Search by image content using OCR via worker container.
- Button for applying actions to multiple images at a time.
- Automatic migration tool for SQLite to MySQL
- Tag not found page for nonexistent tags.
- Custom time zone environment variable.
- Form validation using JS for frontend.
- Messaging for no OCR table.
- Icons on context menu.

### Removed
- Image format being shown in corner.

## [v0.0.9] - 2025-04-21

### Added
- Introduced search functionality.
- Rename tag button.
- Restore all button for trashed images.

### Changed
- Pages no longer use query strings and instead use paths.
- Tags now replace spaces with dashes.
- Search, Tags and Trash now enabled by default.
- File format shown in badge.
- Links are now path based instead of query string based.

### Fixed
- Occasional redirection to a previous page when deleting or restoring images.
- Assign tags field remembers existing tags.
- Allowing removal of tags from an image.

## [v0.0.8] - 2025-01-30

### Added
- Support for displaying images with `.jpeg` extension in addition to `.jpg`.

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
