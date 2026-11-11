# Web Scraping and Crawling

The common scraping vocabulary -- a scrape of one URL, a crawl across a site, and the content they return -- distilled from the APIs that already exist. Part of [Schema Commons](https://github.com/api-commons/schema-commons),
published by the [API Commons](https://apicommons.org).

Built from the providers tagged Web Scraping, Web Crawling, Data Extraction, Browser Automation, Headless Browser, Proxies in [APIs.io](https://apis.io) that
publish their own OpenAPI. Only harvested contracts count -- nothing API Evangelist
generated. Every number below is a count of providers.

## What the market already agrees on

<!-- commons:summary -->
| Concept | Expose it | Readable schema | Core properties (share) | Collection named |
| --- | ---: | ---: | --- | --- |
| scrape | 49 | 44 | url 66% | extract 23, screenshot 22, scrape 17, fetch 6 |
| crawl | 15 | 15 | url 93%, limit 73% | crawl 14, map 5, sitemap 3, crawlers 1 |

Cohort: 109 providers with harvested OpenAPI, 50 crosswalks. Of the providers exposing a scrape: 84% create, 35% list, 8% fetch, 0% update, 2% delete. Generated 2026-11-11 by build.py.
<!-- /commons:summary -->

Shares are of the providers with a readable resource schema for that concept. The
extended tier and the long tail of every concept are in [profile.yml](profile.yml).

## What the measurement shows

- A scrape is a request, not a resource: 44 readable providers agree on the url; formats reaches 41% -- the scraper's output choice (html, markdown, json, screenshot). Rendering, proxy country and wait options are each spelled several ways.
- Crawls agree on url and limit, with status at 47%: a crawl is an asynchronous job bounded by a page limit.

## Artifacts

- [openapi.yml](openapi.yml) -- OpenAPI 3.1 of the shared operations. No one serves it; it
  is the shape to map to. Lints clean against the
  [naming ruleset](https://github.com/api-commons/schema-commons/blob/main/ruleset/schema-commons-naming.yaml).
- [schema/](schema) -- JSON Schema 2020-12 per concept; each property carries
  `x-commons-tier`, `x-commons-share`, `x-commons-providers` and the spellings seen.
- [crosswalk/](crosswalk) -- one per provider, common name -> their name, with the harvested
  spec and operations each mapping was read from.
- [adopters.yml](adopters.yml) -- who exposes which concept, linked to their APIs.io page.
- [concepts.yml](concepts.yml) -- the only hand-written input: concepts, path segments and
  their qualifiers, aliases, reviewed exclusions, merged duplicates, and the decisions below.
- [census/](census) -- the cohort and the raw census the profile is built from.

## Decisions

These are calls, not measurements, recorded so they can be revisited as the method matures.

- formats is the canonical name for the output choice, and render_js for JavaScript rendering.

## Rebuild

```bash
../schema-commons/scripts/run.sh .
```

## License

Artifacts CC BY-NC-SA 4.0 ([LICENSE](LICENSE)); code Apache 2.0 ([LICENSE-CODE](LICENSE-CODE)).
