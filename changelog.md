# Changelog

All notable changes to this project will be documented in this file.

## [v1.1.2] - 2026-07-31

### Added
- Apple Touch Icon for bookmarked pages.
- Private image thumbnail when sent into social chats.
- Additional format for thumbnail extraction to support format `YYYY-MM-DD_HH-MM-SS`.
- Support for creating API keys.

### Fixed
- MP4 files unplayable from share URL.
- Trash multiple selected files failing on folders with spaces.

## [v1.1.1] - 2026-05-04

### Fixed
- Crowded button layout when selecting items on mobile.
- Alignment of grid when display is between 1200px - 992px.
- Generating thumbnails task showing as hanging despite succeeding.

## [v1.1.0] - 2026-05-04

### Added
- Mobile-first UI with two offcanvas sidebars for page navigation and quick actions.
- Context menu on long-press for images.
- Breakdown for storage in sidebar.
- Ability to scroll sidebar if content starts to overflow.
- Custom scroll bars.
- Redirection to 'All Screenshots' from a deleted folder or tag when currently using that page.

### Changed
- Disabled cache on shared links to prevent newly private links from being cached on client systems.
- Delete tag/folder context menu buttons no longer trigger modal.
- Sidebar folder icons (both parent and child).
- Grid layout on mobile shows two in a row instead of a single image.
- Extended cache period on thumbnails to ensure rapid page loads.
- Made text in sidebar bold.
- Default page limit set to 24 (Override with `PAGE_LIMIT`). 
- Headers are sticky to keep controls visible when scrolling.
- Disabled text selection on pagination bar.

### Fixed
- File timestamps updating after moving folders or renaming.
- Trash icon not appearing when folder empty.
- Scrolling twice if window height was not tall enough to fit all elements.

## [v1.0.3] - 2026-05-02

### Added
- Private Sidebar button for easier viewing of images set to private.
- Make private button to multi-select actions.
- Download button to multi-select actions.
- Hold shift to select.
- Select all (on page) button.
- New version available message in footer.
- Generate thumbnail endpoint. 
- Feedback button to footer.

### Changed
- Updated icon library to latest.
- Upgraded to PHP 8.5.
- Icon for active tags now shows a tag (due to icon library updates).
- Moved changelog link into version number.

### Fixed
- Bug where images with capitalised extensions could not be trashed by using "Empty trash" button.

## [v1.0.2] - 2026-05-01

### Added
- Counter when force generating thumbnails.
- Context menu for folders in the sidebar (rename and delete actions).
- Confirm permanently delete popups.
- Restore database backup tool to recover OCR and tags.

### Fixed
- Database export includes numeric array indices as column names, corrupting the backup.
- OCR results not showing within folder context.
- OCR results not showing for images in folders from within a tag context.

## [v1.0.1] - 2026-04-30

### Added
- Clear search function on page type switch.
- Remove tags and Move Folder options to Actions dropdown when searching.

### Changed
- Image caching now has a time limit and processing is limited to 50 items at a time to prevent resource exhaustion.
- Colours in actions dropdown more muted.

### Fixed
- Missing protocol on copy to clipboard.
- Space handling on next page when using folders.
- Space handling when using search in folders.
- Database doesn't update structure when attempting to make an image private.
- Attempted database update when images don't yet exist in the table.
- Restore & Permanently delete selected buttons not working.

## [v1.0.0] - 2026-04-30

> [!CAUTION]  
> The nginx web container has been removed, share links now default to `/share/example.jpg`. To use custom domains please refer to the `examples/compose-traefik.yml` example.

### Added
- Selected images counter.
- Sharing endpoint in photon container.
- Deselect all button.
- Active page indicator for tag pages.
- Context menu for image interactions.
- File metadata inside context menu.
- Context menu for tags in the sidebar (rename and delete actions).
- Sorting for images (date, size and name).
- Selection across multiple pages at a time for better management.
- Sticky pagination bar, prevents moving when item count is lower between pages.
- Ability to make images private, links will only work with a valid session.
- Favicon and logo to footer.
- Better backend reporting for uploads.
- New compose files for updated deployments.
- Ability to move items between folders.
- Animations on hover.
- GitHub button in footer linking to project.

### Changed
- Environment variables `ADMIN_DOMAIN` and `SHARE_DOMAIN` replaced with `PHOTON_DOMAIN` and `PHOTON_SHARE_DOMAIN`.
- Search now acts as a filter on a given page context.
- File names now only available in the context menu.
- Image selection highlights border, shrinks and darkens image.
- Images now have rounded corners to match the design language.
- Compression now limits image dimensions to further decrease storage consumption.
- Backup file name now contains timestamp.
- Simplified backend functions for easier maintainability.
- Upload limits have been raised for mass-uploading.

### Fixed
- Screenshots with special characters in the name cannot be selected by clicking.
- Restoring a file from trash will always go back to root folder regardless of original source.
- Image does not scale correctly when changing column count.
- Assigning tags after first page redirects you to the start.
- Renaming an image results in tags being lost - resulting in orphaned attachments.
- Renaming an image results in thumbnails being regenerated and creating duplicates. 
- 'All Screenshots' in sidebar doesn't show subfolder count.
- Going to a folder by link doesn't show it as active in the sidebar
- Image counter for folders doesn't update on upload.
- Uploading an image with the same name as existing will replace it without confirmation.
- Image counters don't update on deletion.
- Newly created tags do not show up in the delete menu until a full-page refresh has occurred.
- Delete tag dropdown doesn't dynamically update if a tag has been deleted.

### Removed
- Autocompletion on rename form for previously entered names.
- Secondary web container.
- Option for two columns.
- Menu button on images.
- URL scheme settings.
- Checkbox on images.
- SQLite to MySQL migration tool.

## [v0.1.4] - 2026-04-24

> [!TIP]
> Web container is being removed in the next update, update your compose files on the next update.

### Added
- Folders for better file management, items in folders can also have tags.
- Ability to untag selected images instead of removing tags one at a time.

### Changed
- Upload destination can now be selected when there are new folders.

### Fixed
- Bug where pagination would display pages that don't exist.

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
