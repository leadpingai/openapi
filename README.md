[![](https://img.shields.io/github/last-commit/leadpingai/openapi?style=for-the-badge)](https://github.com/leadpingai/openapi/commits/main)
[![](https://img.shields.io/github/license/leadpingai/openapi?style=for-the-badge)](https://github.com/leadpingai/openapi/blob/main/LICENSE)
[![](https://img.shields.io/github/actions/workflow/status/leadpingai/openapi/codeql.yml?label=CodeQL&style=for-the-badge)](https://github.com/leadpingai/openapi/actions/workflows/codeql.yml)

# ![Leadping](https://leadping.ai/favicon.ico) Leadping OpenAPI

The official OpenAPI 3 specification for the Leadping API: a machine-readable contract for building lead management, messaging, calling, automation, reporting, billing, and business integrations with Leadping.

This repository is the source for Leadping API documentation, client tooling, and generated SDKs. Use the hosted [Leadping OpenAPI specification](https://leadping.ai/docs/openapi.json) to inspect request and response schemas, validate integrations, generate a custom API client, or power OpenAPI-compatible developer tools.

New to the API? Start with the [Leadping API introduction](https://leadping.ai/docs/introduction), then use the [API reference](https://leadping.ai/docs/api-reference) for endpoint details.

## Download the specification

Download the currently published contract from Leadping:

```bash
curl -fsSLo leadping-openapi.json https://leadping.ai/docs/openapi.json
```

The hosted document is the canonical specification for the production API.

## API Server

Production API requests use:

```text
https://api.leadping.ai
```

## Authentication

Leadping API clients authenticate with the Bearer scheme:

| Credential | Authorization header | Intended use |
| --- | --- | --- |
| WorkOS organization API key | `Bearer sk_...` | Services, agents, and organization integrations |
| Leadping user access token | `Bearer <user-token>` | Operations performed for a signed-in user |
| Leadping source key | `Bearer lp_src_...` | Approved lead-ingestion endpoints only |

```http
Authorization: Bearer sk_example
```

Source keys are rejected by non-ingestion endpoints. See [API authentication](https://leadping.ai/docs/api-authentication) for credential details.

## Official Leadping SDKs

Leadping publishes type-safe SDKs generated from this OpenAPI contract. For production integrations, choose the package for your language:

| Language | Package | Repository |
| --- | --- | --- |
| TypeScript / JavaScript | [`@leadping/sdk`](https://www.npmjs.com/package/@leadping/sdk) | [leadping-typescript](https://github.com/leadpingai/leadping-typescript) |
| Python | [`leadping`](https://pypi.org/project/leadping/) | [leadping-python](https://github.com/leadpingai/leadping-python) |
| .NET | [`Leadping.OpenApiClient`](https://www.nuget.org/packages/Leadping.OpenApiClient/) | [leadping-dotnet](https://github.com/leadpingai/leadping-dotnet) |
| Go | [`github.com/leadpingai/leadping-go`](https://pkg.go.dev/github.com/leadpingai/leadping-go) | [leadping-go](https://github.com/leadpingai/leadping-go) |
| PHP | [`leadpingai/sdk`](https://packagist.org/packages/leadpingai/sdk) | [leadping-php](https://github.com/leadpingai/leadping-php) |
| Java | [`ai.leadping:leadping`](https://central.sonatype.com/artifact/ai.leadping/leadping) | [leadping-java](https://github.com/leadpingai/leadping-java) |

## Use the specification

You can use `openapi.json` with OpenAPI-compatible tooling such as Swagger UI, Redoc, Microsoft Kiota, or OpenAPI Generator.

Validate with Redocly:

```bash
npx @redocly/cli lint openapi.json
```

Generate a TypeScript client with Kiota:

```bash
kiota generate --openapi openapi.json --language typescript --class-name LeadpingOpenApiClient --namespace-name leadping
```

Prefer an official SDK for production use. Generate a custom client for unsupported languages or custom packaging.

## Contributing

Open an issue for documentation problems, schema mismatches, or feature requests. Include the affected path, operation, expected behavior, and observed behavior. Remove credentials and customer data from examples.

Do not report security vulnerabilities in public issues. Follow `SECURITY.md` instead.

## License

This repository is licensed under the MIT License.
