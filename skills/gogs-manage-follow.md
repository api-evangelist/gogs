---
name: gogs-manage-follow
description: Follow or unfollow a user and verify the follow status.
api: openapi/gogs-openapi.json
operations:
- checkFollowing
- followUser
- unfollowUser
generated: '2026-09-21'
method: generated
generator: extract-docs-artifacts.py skills (local)
source: openapi/gogs-openapi.json ; every operationId checked against the contract
---

# gogs-manage-follow

Follow or unfollow a user and verify the follow status.

## Steps

1. 1. Use `checkFollowing` with header `Authorization: Bearer <token>` and path parameter `target` to see if you already follow the user.
2. 2. Use `followUser` with header `Authorization: Bearer <token>` and path parameter `target` to follow the user (PUT is idempotent).
3. 3. Use `checkFollowing` again with the same header and `target` to confirm the follow succeeded.
4. 4. Use `unfollowUser` with header `Authorization: Bearer <token>` and path parameter `target` to unfollow the user (DELETE).
5. 5. Use `checkFollowing` a final time with the same header and `target` to verify the user is no longer followed.

## Rules

- Authentication: Include an `Authorization` header with a valid AccessToken (Bearer token) for all operations.
- Idempotency: `followUser` (PUT) is idempotent; repeated calls with the same `target` have no additional effect.
- Path parameters: All operations require the `target` username as a path parameter.
- Errors: The API returns standard HTTP error codes (e.g., 401 for unauthorized, 404 if the target user does not exist).
