# Security Policy

Open Dick Project handles sensitive subject matter. Security mistakes can harm contributors.

## Public Repository Boundary

The public repository must not contain:

- raw submitted photos
- private submission metadata
- deletion request logs
- API tokens
- Cloudflare credentials
- local machine paths
- private app runtime logs

The public repository may contain:

- documentation
- source code intended for public release
- synthetic examples
- annotation schema
- aggregate-only metrics

## Raw Data Policy

Raw photos are private operational data.

They should be stored only in controlled private storage and must never be committed to GitHub.

## Deletion Policy

Each submission should have a deletion ID. A contributor can request deletion with that ID.

Deletion must remove or tombstone:

- raw image
- submission metadata
- unmerged annotation derived from the submission

Future training manifests must exclude deleted IDs.

## Vulnerability Reports

Do not open a public issue containing sensitive details.

For now, report security concerns privately to the project operator.

## Minimum Operational Checks

Before opening collection to more users, verify:

- `/data/` is not publicly reachable
- `.git/` is not publicly reachable
- `.tools/` and local logs are not publicly reachable
- submitted raw images are not served as static files
- upload endpoints have size limits
- expensive model endpoints have rate limits
- public documentation does not contain personal names, local paths, or credentials

## Prototype Server Controls

The private prototype server should keep these controls enabled before any public collection link is shared:

- public static files are served from an allowlist only
- the public domain points only at the Open Dick Project collector, not any measurement prototype
- `/data/`, `.git/`, `.tools/`, local logs, scripts, and docs are not served
- upload APIs accept JSON only
- request bodies have a hard size limit
- upload and model endpoints have rate limits
- saved submission metadata is size-limited and sanitized
- responses include CSP, frame blocking, MIME sniffing protection, and no-referrer headers
- analytics must not send raw images, deletion IDs, mask geometry, size, country, age, or other contribution data

For a broader beta, add Cloudflare WAF/rate limiting, private object storage, backup rules, access logs review, and a tested deletion workflow.

## Current Status

Early prototype. Treat all collection infrastructure as private until the storage, deletion, moderation, and review process has been tested.
