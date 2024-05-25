# smithy-gh-pages-action
[WORK IN PROGRESS]

GitHub Action to generate API documentation from Smithy models and deploy to GitHub Pages.

### Usage
See [action.yml](https://github.com/msayson/smithy-gh-pages-action/action.yml)

```yaml
- name: Generate API docs from Smithy models and deploy to GitHub Pages
  uses: msayson/smithy-gh-pages@v0.1
  with:
    # Name of the Gradle task to generate the OpenAPI JSON spec from Smithy models
    # Default: build
    gradle-smithy-task-name: 'REPLACE_WITH_GRADLE_TASK_NAME'
    # Filepath of the OpenAPI JSON spec generated by your Smithy models package
    openapi-json-filepath: 'REPLACE_WITH_YOUR_OPENAPI_JSON_FILEPATH'
    # Directory to create/use for generating the OpenAPI YAML spec
    openapi-yaml-directory: 'REPLACE_WITH_NEW_OPENAPI_YAML_DIR'
    # Directory to create/use for generating the API docs HTML
    api-docs-directory: 'REPLACE_WITH_NEW_API_HTML_DOCS_DIR'
```

Example usage by [msayson/consent-management-api-models](https://github.com/msayson/consent-management-api-models):

```yaml
- name: Generate API docs from Smithy models and deploy to GitHub Pages
  uses: msayson/smithy-gh-pages@v1
  with:
    gradle-smithy-task-name: build
    openapi-json-filepath: build/smithyprojections/consent-management-api-models/source/openapi/ConsentManagementApi.openapi.json
    openapi-yaml-directory: build/openapi
    api-docs-directory: build/docs
```
