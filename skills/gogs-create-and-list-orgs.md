---
name: gogs-create-and-list-orgs
description: Create a new organization and then list all organizations you belong to.
api: openapi/gogs-openapi.json
operations:
- createMyOrg
- listMyOrgs
generated: '2026-09-21'
method: generated
generator: extract-docs-artifacts.py skills (local)
source: openapi/gogs-openapi.json ; every operationId checked against the contract
---

# gogs-create-and-list-orgs

Create a new organization and then list all organizations you belong to.

## Steps

1. 1. `createMyOrg` – send a POST request to `/user/orgs` with the required JSON body fields for the new organization (e.g., name, description).
2. 2. `listMyOrgs` – send a GET request to `/user/orgs` to retrieve the list of your organizations.

## Rules

- Include an `Authorization: Bearer <access-token>` header (AccessToken scheme).
- Use the same access token for both requests.
