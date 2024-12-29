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
