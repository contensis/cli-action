# Contensis cli action

This action allows you to interact with Contensis CMS via cli commands in your own Github Actions

## Inputs

## `alias`

**Required** 'The Contensis cloud alias to connect to'

## `project-id`

The id of the project to connect to. Default: `"website"`

## `client-id`

**Required** Client id to connect to the supplied alias

## `shared-secret`

**Required** Shared secret to use with the supplied client id

## Outputs

No outputs are implemented as yet.

## Example usage

### Get entries and output to a file

```yml
uses: contensis/cli-action@v1
with:
  command: get entries --zenql "sys.contentTypeId = blogPost" --ouput ./data/blogPosts.json
  alias: example-dev
  project-id: contensis
  client-id: ${{ secrets.CONTENSIS_CLIENT_ID }}
  shared-secret: ${{ secrets.CONTENSIS_SHARED_SECRET }}
```

### Create a content type from a file

```yml
uses: contensis/cli-action@v1
with:
  command: create contenttype blogPost --from-file ./content-models/blogPost.json
  alias: example-dev
  project-id: contensis
  client-id: ${{ secrets.CONTENSIS_CLIENT_ID }}
  shared-secret: ${{ secrets.CONTENSIS_SHARED_SECRET }}
```
