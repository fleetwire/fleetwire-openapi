# Fleetwire OpenAPI spec

The OpenAPI 3.1 description of the [Fleetwire](https://fleetwire.io) API: listings, availability, quotes, bookings, customers and webhooks for independent rental businesses.

**Read the docs:** [docs.fleetwire.io](https://docs.fleetwire.io). The docs are built from this same file.

| | |
|---|---|
| File | [`openapi.json`](openapi.json) |
| Base URL | `https://api.fleetwire.io/api` |
| Auth | Bearer API token from **Settings → Security → API Tokens** in Fleetwire |

## Use it

**Postman or Insomnia:** import `openapi.json` directly, or by URL:

```
https://raw.githubusercontent.com/fleetwire/fleetwire-openapi/main/openapi.json
```

**Generate a client**, for example TypeScript:

```bash
npx @openapitools/openapi-generator-cli generate -i https://raw.githubusercontent.com/fleetwire/fleetwire-openapi/main/openapi.json -g typescript-fetch -o ./fleetwire-client
```

Swap `-g` for `php`, `python`, `go`, `ruby` and so on.

**First request:**

```bash
curl https://api.fleetwire.io/api/v2/listings -H "Authorization: Bearer $FLEETWIRE_TOKEN" -H "Accept: application/json"
```

## Two APIs in one file

- **Host API** (`/v2/…`): for a rental business working with its own account. Tag names without a prefix.
- **Partner API** (`/partners/v1/…`): for toll, violation and other service providers working across hosts who have opted in. Tags start with `Partner API:`. It uses a partner key (`fwp_…`) that Fleetwire issues; ask through the chat on [fleetwire.io](https://fleetwire.io).

## Prefer no code?

- **AI assistants:** connect Claude or ChatGPT to your fleet through the MCP server at `https://api.fleetwire.io/mcp`. See [fleetwire.io/ai](https://fleetwire.io/ai/).
- **Zapier:** [Fleetwire on Zapier](https://zapier.com/apps/fleetwireio/integrations).

## Feedback

Found something the spec gets wrong, or an endpoint you need? [Open an issue](https://github.com/fleetwire/fleetwire-openapi/issues).

This repo is published from Fleetwire's main codebase, so pull requests can't be merged directly, but issues are read and fixed there.
