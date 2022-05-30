# fhir-package-registry-pipeline

GitHub Action Pipeline for version management of FHIR conformance resource using a [FHIR package](https://registry.fhir.org/learn), including:
  * create a FHIR package
  * commit the package itself to a Git repo for safekeeping
  * update the a FHIR package registry feed 

The current pipeline allows to manage a FHIR package feed fully in GitHub, no external hosting needed.

<img align="center" width="40%" src="fhir-package-registry-pipeline.png">

1. Develop your FHIR conformance resources on GitHub. Execution of FHIR Shorthand and validation of generated artefacts can be achieved using [Firely Terminal Pipeline](https://github.com/FirelyTeam/firely-terminal-pipeline/).
2. The created package needs to be publicly accessible to be indexed by the [FHIR Package Registry](https://registry.fhir.org). The package generated by this pipeline can therefore be commited to a public Git repo.
3. The [FHIR package feed](https://registry.fhir.org/submit) will be updated automatically based on the information provided by the package.json of the generated package.

## Options

You can specify the following options using the ["with" syntax](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions#jobsjob_idstepswith) in your GitHub Actions yml configuration:

 * SIMPLIFIER_USERNAME:<br>
    description: 'Simplifier email address (not username), needed for running Quality Control checks. Please use GitHub Secrets for this variable.'<br>
    required: true
 * SIMPLIFIER_PASSWORD:<br>
    description: 'Simplifier password, needed for running Quality Control checks. Please use GitHub Secrets for this variable.'<br>
    required: true
 * PACKAGE_FEED_REPO_PATH:<br>
   description: 'Relative path to the package feed repository, repository will be used to extract the package feed and store the FHIR package itself'<br>
   required: true
 * PATH_TO_CONFORMANCE_RESOURCES:<br>
   description: 'Relative path to folder with conformance resources incl. package.json'<br>
   required: true
 * BASE_URL_PACKAGE_FEED:<br>
   description: 'Base url incl. subpath of the FHIR package feed'<br>
   required: true
 * PACKAGE_FEED_FILE_NAME:<br>
   description: 'Filename of the FHIR package feed which shall be updated'<br>
   required: true
 * PATH_TO_PACKAGE_STORAGE:<br>
   description: 'Path to parent folder in which all packages are to be stored in Git'<br>
   required: true
