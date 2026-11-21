# .github

Organization-wide GitHub configuration for Chronos.

- `profile/README.md`: the organization's landing page.
- `.github/workflows/publish-image.yml`: reusable workflow that builds a repo's Dockerfile and publishes it to `ghcr.io/chronos-packet-scheduler/<repo>`. Every service repo calls it from its own `ci.yml`.
