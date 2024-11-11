# Remove Database Client (QueryDesk)

Automate setting up a database client using https://devhub.tools so your
team has instant access for debugging and testing.

This action allows you to cleanup connections that were previously created.

## Usage

```yaml
jobs:
  create_db:

    steps:
    # ...

    - name: Remove Database Client
      uses: QueryDesk/remove-db-client@v1
      with:
        api-key: ${{ secrets.DEVHUB_API_KEY}}
        id: pr-${{ github.event.pull_request.number }} # your workflow trigger must be `pull_request` for this to work and must match the id passed on create

    # ...
```

## Inputs

-   `api-key`: (Required) You will need to create an API key on
    https://app.devhub.tools/settings?tab=api_keys and save it as a secret in GitHub
    Actions settings.

    Example API key:

    ```text
    dh_WHDrEa82t8mHwTvZqEdgA79dgLk3N3x1aehmjps68PHXwt6qxfgzBKFStPizLpPij3BM1cnfgtGcYipt5ZJUeV
    ```

-   `id`: (Required) The id that was used to create the database connection.

-   `host`: (Optional) The host to make the api call to, defaults to api.querydesk.com.
