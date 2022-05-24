# release-fhir-package-pipeline

GitHub Action Pipeline for version management of FHIR conformance resource using a [FHIR package](https://registry.fhir.org/learn), including:
  * update the a FHIR package registry feed 
  * commit the package itself to a Git repo for safekeeping

## Options

You can specify the following options using the ["with" syntax](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions#jobsjob_idstepswith) in your GitHub Actions yml configuration:

* SIMPLIFIER_USERNAME:
   - description: 'Simplifier email address (not username), needed for running Quality Control checks. Please use GitHub Secrets for this variable.'
   - required: true
* SIMPLIFIER_PASSWORD:
   - description: 'Simplifier password, needed for running Quality Control checks. Please use GitHub Secrets for this variable.'
   - required: true
