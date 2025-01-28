# Photon Screenshot Dashboard

The PHP Screenshot Management Dashboard

To deploy Photon, use the included `docker-compose-example.yml`.

Ensure you have a data folder that contains your screenshots. Current supported mimetypes are `JPG`, `PNG`, `GIF` and `MP4`.

```
services:
  photon:
    container_name: photon_dashboard
    image: git.jrdn.dev/jordanwalster/photon-dashboard:latest
    ports:
      - 8090:80
    volumes:
      - type: bind
        source: ./data
        target: /var/www/html/data
        bind:
          propagation: rshared
    environment:
      ADMIN_DOMAIN: photon.jrdn.dev
      SHARE_DOMAIN: ss.example.com
      USER_EMAIL: me@example.com
```

There are additional environment variables that can be set to enable experimental features (defaults are set to false):


| Environment Variable | Values            | Default | Description                        |
| -------------------- |:-----------------:|:-------:| ---------------------------------- |
| TAGS_ENABLED         | `true` \| `false` |  false  | Enables the tagging functionality  |
| SEARCH_ENABLED       | `true` \| `false` |  false  | Enables screenshot search          |
| PAGE_LIMIT           | `int`             |   24    | Override the default page limit    |

You can find the container image history [here](https://git.jrdn.dev/jordanwalster/-/packages/container/photon-dashboard/versions).

# Changelog

## [v0.0.4] (The Tag Update) - 2025-01-28

### Added

- Update compose file to use bind mount
- Delete tag button
- Added image tag pagination
- Tagged Screenshots pages
- Override for default page limit 

### Fixed

- Bug where selected tags from a previous image wouldn't clear correctly after modal close

## [v0.0.3] - 2025-01-27

### Added

- Filter buttons for mimetype
- Tag attachment counter
- Image tagging
- Support for tag creation


## [v0.0.2] - 2025-01-26

### Added

- Gravatar profile pictures
- Download image function
- Flags for disabling incomplete functions (search, tagging)

## [v0.0.1] - 2025-01-25

### Added

- Image format labels to dashboard
- Rename image function
- Copy link to clipboard function
- A changelog to document changes
