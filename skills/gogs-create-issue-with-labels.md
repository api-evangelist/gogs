---
name: gogs-create-issue-with-labels
description: Create a new issue in a repository and assign labels to it.
api: openapi/gogs-openapi.json
operations:
- createIssue
- addIssueLabels
generated: '2026-09-21'
method: generated
generator: extract-docs-artifacts.py skills (local)
source: openapi/gogs-openapi.json ; every operationId checked against the contract
---

# gogs-create-issue-with-labels

Create a new issue in a repository and assign labels to it.

## Steps

1. 1. Call `createIssue` with the required request body (title, optional body) and include the `Authorization` header.
2. 2. Call `addIssueLabels` with the issue index returned from step 1, providing the label IDs in the request body and include the `Authorization` header.

## Rules

- Authentication: include an `Authorization: Bearer <access-token>` header (AccessToken scheme).
- Idempotency: the `createIssue` operation is not idempotent; avoid duplicate calls.
- Error handling: expect standard HTTP error codes (4xx for client errors, 5xx for server errors).
