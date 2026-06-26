# Contributing

Thanks for helping improve the Leadping OpenAPI specification.

## Before You Start

- Search existing issues and pull requests before opening a new one.
- Use the bug, documentation, or feature issue templates when they fit.
- Report security vulnerabilities privately by following `SECURITY.md`.

## Pull Requests

- Keep changes focused and easy to review.
- Include a clear description of the endpoint, schema, or documentation problem.
- Explain backward-compatibility impact for API contract changes.
- Avoid unrelated formatting or generated-file churn.

## API Contract Changes

This repository is the source contract for generated Leadping SDKs and API documentation. Changes to `openapi.json` can affect multiple languages and package releases, so include enough context for reviewers to understand the downstream impact.

When changing the contract, check:

- Operation IDs are stable and descriptive.
- Request and response schemas are accurate.
- Required fields, nullable fields, and enum values match API behavior.
- Error responses are documented.
- Descriptions are clear enough for generated SDK docs.

## License

By contributing, you agree that your contribution is licensed under the MIT License.
