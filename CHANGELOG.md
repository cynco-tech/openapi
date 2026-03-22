# Changelog

All notable changes to the Cynco OpenAPI specification are documented here.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [1.0.0] - 2026-03-22

### Added

- Initial OpenAPI 3.1 specification for the Cynco REST API v1.
- **Invoices**: GET list, GET by ID, PATCH update, POST batch.
- **Customers**: GET list, GET by ID, POST create, PATCH update, DELETE, POST batch.
- **Vendors**: GET list, GET by ID, POST create, PATCH update, DELETE, POST batch.
- **Bills**: GET list, GET by ID, PATCH update.
- **Items**: GET list, GET by ID, PATCH update, DELETE.
- **Accounts**: GET list (chart of accounts).
- **Journal Entries**: GET list, GET by ID, POST create, POST batch.
- **Bank Accounts**: GET list.
- **Bank Transactions**: GET list.
- **Reports**: GET trial balance, GET balance sheet, GET profit & loss.
- Bearer token authentication with `cak_` prefix keys.
- Offset and cursor pagination.
- Field selection via `?fields=` parameter.
- Idempotency-Key header for write operations.
- Rate limit headers (X-RateLimit-Limit, X-RateLimit-Remaining, X-RateLimit-Reset).
- ETag caching on GET endpoints.
- Webhook event documentation (HMAC-SHA256 signing).
- Complete error envelope with typed error codes.
- CI validation workflow using Redocly.
