# cd-nixpacks
Opinionated continuous delivery action based on nixpacks

```yaml
name: CD
on:
  push:
    branches: [main]
jobs:
  build:
    runs-on: ubuntu-latest
    permissions:
      contents: read
      packages: write
    steps:
      - uses: actions/checkout@v4
      - uses: dtinth/cd-nixpacks@main
        with:
          preset: build-amd64
```

## Presets

| Preset name | Behavior |
| --- | --- |
| build-multiarch (default) | Builds an amd64+arm64 multi-architecture image. Image can be deployed to arm64 hosts, but requires more time to build. |
| build-amd64 | Builds an amd64 image. |
