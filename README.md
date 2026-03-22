# Cynco OpenAPI Specification

[![OpenAPI 3.1](https://img.shields.io/badge/OpenAPI-3.1-6BA539?logo=openapiinitiative&logoColor=white)](https://spec.openapis.org/oas/v3.1.0)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

The official OpenAPI specification for the [Cynco](https://cynco.io) REST API. This is the single source of truth from which SDKs, documentation, and Postman collections are generated.

---

## Quick Links

| Resource | URL |
|----------|-----|
| Interactive API docs | [app.cynco.io/docs/api](https://app.cynco.io/docs/api) |
| Dashboard & API keys | [app.cynco.io/settings/api](https://app.cynco.io/settings/api) |
| Status page | [status.cynco.io](https://status.cynco.io) |

---

## What's in this spec

The Cynco API covers the full lifecycle of business financial data:

- **Invoices** -- list, get, update, batch create
- **Customers** -- full CRUD + batch create
- **Vendors** -- full CRUD + batch create
- **Bills** -- list, get, update
- **Items** -- list, get, update, delete
- **Accounts** -- chart of accounts (read-only)
- **Journal Entries** -- list, get, create, batch create
- **Bank Accounts** -- list, get (read-only)
- **Bank Transactions** -- list (read-only)
- **Reports** -- trial balance, balance sheet, profit & loss

All endpoints use Bearer token authentication with `cak_`-prefixed API keys, support field selection, and follow a consistent response envelope.

---

## Using the spec

### Validate

```bash
npm install
npx @redocly/cli lint openapi.yaml
```

### Generate an SDK

Use any OpenAPI-compatible generator. For example, with [openapi-generator-cli](https://openapi-generator.tech/):

```bash
npx @openapitools/openapi-generator-cli generate \
  -i openapi.yaml \
  -g typescript-fetch \
  -o ./sdk-typescript
```

### Import to Postman

1. Open Postman
2. Click **Import**
3. Select `openapi.yaml` from this repository
4. All endpoints, parameters, and examples will be imported automatically

### Preview documentation locally

```bash
npx @redocly/cli preview-docs openapi.yaml
```

This starts a local server at `http://localhost:8080` with interactive API documentation.

---

## Repository structure

```
openapi/
  openapi.yaml          -- The OpenAPI 3.1 specification
  package.json          -- Validation tooling (Redocly)
  .github/
    workflows/
      validate.yml      -- CI: validates the spec on every PR
  LICENSE               -- MIT
  CHANGELOG.md          -- Version history
```

---

## Versioning

This spec follows the Cynco API version. The current API version is `v1`. Breaking changes result in a new API version; additive changes (new fields, new endpoints) are released within the current version and documented in [CHANGELOG.md](CHANGELOG.md).

---

## Changelog

See [CHANGELOG.md](CHANGELOG.md) for the full version history.

---

## Contributing

1. Create a branch from `main`
2. Edit `openapi.yaml`
3. Run `npx @redocly/cli lint openapi.yaml` to validate
4. Open a pull request -- CI will validate the spec automatically
5. Get a review and merge

When adding a new endpoint:
- Add the path under the appropriate tag
- Add or reuse component schemas
- Include at least one example response
- Update CHANGELOG.md

---

## License

MIT -- see [LICENSE](LICENSE) for details.

Copyright 2026 Cynco Sdn Bhd.
