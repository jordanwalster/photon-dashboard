# Photon Dashboard

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
      - ./data:/var/www/html/data
    environment:
      ADMIN_DOMAIN: photon.jrdn.dev
      SHARE_DOMAIN: ss.example.com
      USER_EMAIL: me@example.com
```

There are additional environment variables that can be set to enable experimental features (defaults are set to false):


| Environment Variable | Values            | Description                        |
| -------------------- | ----------------- | ---------------------------------- |
| TAGS_ENABLED         | `true` \| `false` | Enables the tagging functionality  |
| SEARCH_ENABLED       | `true` \| `false` | Enables screenshot search          |

You can find the container image history [here](https://git.jrdn.dev/jordanwalster/-/packages/container/photon-dashboard/versions).

# Changelog

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
