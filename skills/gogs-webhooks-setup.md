---
name: gogs-webhooks-setup
description: Create, list, edit, and delete repository webhooks in Gogs.
api: openapi/gogs-openapi.json
operations:
- listHooks
- createHook
- editHook
- deleteHook
generated: '2026-09-21'
method: generated
generator: extract-docs-artifacts.py skills (local)
source: openapi/gogs-openapi.json ; every operationId checked against the contract
---

# gogs-webhooks-setup

Create, list, edit, and delete repository webhooks in Gogs.

## Steps

1. 1. Use `listHooks` with path parameters `owner` and `repo` to retrieve existing hooks.
2. 2. Use `createHook` with path parameters `owner` and `repo` and a JSON body describing the hook to add a new webhook.
3. 3. Use `editHook` with path parameters `owner`, `repo`, and `id` and a JSON body of the updated fields to modify an existing webhook.
4. 4. Use `deleteHook` with path parameters `owner`, `repo`, and `id` to remove a webhook.

## Rules

- Include an `Authorization` header with a valid AccessToken (apiKey) for all requests.
