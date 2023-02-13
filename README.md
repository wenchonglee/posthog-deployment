## For Linux:

- Just follow https://posthog.com/docs/self-host/open-source/deployment

## For Windows:

1. Git clone posthog repo into this directory `./posthog` 
1. Run `docker-compose up -d`

### Notes:

- `docker-compose.base.yml` is mostly untouched 
- `compose/start` and `compose/wait` must be in `LF` if written in Windows
- `posthog/docker/clickhouse` and `posthog/idl` must be brought in from posthog's git repository, because they are mounted
- `SECRET_KEY` and `SITE_URL` seems to be necessary (even if its just localhost)? but `SENTRY_DSN` isn't
- `caddy` was removed

### More notes

- There seemed to be some automated downloads from public repositories in `posthog-plugins`, not sure if it will impact us
- If we want to update this in the future, it should be decomposed into k8s specs and diffed accordingly

