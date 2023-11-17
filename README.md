This repository provides a common Azure DevOps pipeline template (`publishTestResults.yml`) that simplifies the process of Test Results. By using this template, you can easily publish the test results of your Azure pipelines.


### Parameters used
| Name  | type | Default | Values | Optional/Required | Comments |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| testResultsFormat | string | | | Required | |
| testResultsFiles | string | | | Required | |
| mergeTestResults | string | | | Required | |
| failTaskOnFailedTests | string | | | Required | |
 

### Usage

To use this template, follow these steps:

1. Include the `publishTestResults.yml` file in your Azure DevOps repository.

2. In your Azure DevOps pipeline YAML file, add the following code to reference the template:

```yaml
resources:
  repositories:
    - repository: publishTestResults
      type: GitHub
      name: githubServiceConnection
      ref: <respective branch name>
      endpoint: 'Duck Creek'
steps:
- template: frameWork/common/pipeline/publishTestResults.yml@publishTestResults
  parameters:
      testResultsFormat: ${{parameters.testResultsFormat}}
      testResultsFiles: ${{parameters.testResultsFiles}}
      mergeTestResults: ${{parameters.mergeTestResults}}
      failTaskOnFailedTests: ${{parameters.failTaskOnFailedTests}}
```
