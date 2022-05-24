# fhir-package-registry-pipeline

GitHub Action Pipeline for version management of FHIR conformance resource using a [FHIR package](https://registry.fhir.org/learn), including:
  * create a FHIR package
  * commit the package itself to a Git repo for safekeeping
  * update the a FHIR package registry feed 

The current pipeline allows to manage a FHIR package feed fully in GitHub, no external hosting needed.

## Options

You can specify the following options using the ["with" syntax](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions#jobsjob_idstepswith) in your GitHub Actions yml configuration:

* SIMPLIFIER_USERNAME:
   - description: 'Simplifier email address (not username), needed for running Quality Control checks. Please use GitHub Secrets for this variable.'
   - required: true
* SIMPLIFIER_PASSWORD:
   - description: 'Simplifier password, needed for running Quality Control checks. Please use GitHub Secrets for this variable.'
   - required: true
