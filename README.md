# dream-up

Deploy resources with DReAM CLI up command

## Usage

```yaml
      - name: Deploy
        uses: novodream/dream-up@main
        with:
          workspace: staging
          private-key: ${{ secrets.STAGING_PRIVATE_KEY }}
          production: true # Do not deploy dev dependencies
```

This action is typically used in conjunction with [novodream/setup-dream](https://github.com/novodream/setup-dream)
action.

```yaml

steps:
  - uses: actions/checkout@v3
    with:
      fetch-depth: 0 # not mandatory but required by certain DReAM packages

  - name: Setup DReAM CLI
    uses: novodream/setup-dream@main
    with:
      token: ${{ secrets.DREAM_TOKEN }}
      
  - name: Deploy
    uses: novodream/dream-up@main
    with:
      workspace: staging
      private-key: ${{ secrets.STAGING_PRIVATE_KEY }}
      production: true # Do not deploy dev dependencies, default is true
```
