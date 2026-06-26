# Leadping OpenAPI

Official OpenAPI specification for the Leadping API.

This repository publishes the machine-readable API contract used by Leadping documentation, client tooling, and generated SDKs. The specification describes Leadping endpoints for lead intake, messaging, calling, automations, billing, business settings, and compliant lead communication workflows.

Documentation is available at [leadping.ai/docs](https://leadping.ai/docs).

## API Server

Production API requests use:

```text
https://api.leadping.ai
```

## Authentication

Leadping API clients authenticate with one of the supported request headers:

```http
Authorization: Bearer <token>
```

```http
X-Leadping-Api-Key: <key>
```

Use the credential type that matches your Leadping integration.

## SDKs

Leadping publishes generated SDKs from this OpenAPI contract:

| Language | Repository |
| --- | --- |
| TypeScript | [leadping-typescript](https://github.com/leadpingai/leadping-typescript) |
| Python | [leadping-python](https://github.com/leadpingai/leadping-python) |
| .NET | [leadping-dotnet](https://github.com/leadpingai/leadping-dotnet) |
| Go | [leadping-go](https://github.com/leadpingai/leadping-go) |
| PHP | [leadping-php](https://github.com/leadpingai/leadping-php) |
| Java | [leadping-java](https://github.com/leadpingai/leadping-java) |

## Using the Specification

You can use `openapi.json` with OpenAPI-compatible tooling such as Swagger UI, Redoc, Microsoft Kiota, or OpenAPI Generator.

Example validation:

```bash
npx @redocly/cli lint openapi.json
```

Example SDK generation with Kiota:

```bash
kiota generate --openapi openapi.json --language typescript --class-name LeadpingOpenApiClient --namespace-name leadping
```

Prefer the official Leadping SDK repositories for production use. Generate clients directly from this repository when you need custom packaging, local experiments, or unsupported target languages.

## Contributing

Open an issue for documentation problems, schema mismatches, or feature requests. If an API contract change is needed, describe the endpoint, expected behavior, and any backward-compatibility concerns.

Do not report security vulnerabilities in public issues. Follow `SECURITY.md` instead.

## License

This repository is licensed under the MIT License.
