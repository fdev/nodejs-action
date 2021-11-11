# NodeJS Action :package:

1. Installs NodeJS based on version defined in `.nvmrc`.
2. Runs `npm ci`.
3. Caches `node_modules` for subsequent runs with the same `package-lock.json` and NodeJS version.

## Usage

```
name: Build
on: push

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@v2

      - name: Setup NodeJS
        uses: fdev/nodejs-action@v1

      - name: Build
        run: npm run build
```


## Outputs

| Name           | Description                                 |
|----------------|---------------------------------------------|
| `node_version` | NodeJS version that was read from `.nvmrc`. |
