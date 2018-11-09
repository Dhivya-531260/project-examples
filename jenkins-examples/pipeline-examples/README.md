# Jenkins Pipeline - Working With Artifactory

## Introduction
The Pipeline Jenkins Plugin allows you to create a script that defines your build steps. 
For those not familiar with Jenkins Pipeline, check out the [Pipeline Tutorial](https://github.com/jenkinsci/pipeline-plugin/blob/master/TUTORIAL.md) or the [Getting Started With Pipeline](https://jenkins.io/doc/pipeline/) documentation.

The Artifactory Pipeline DSL documentation is available [here](https://wiki.jenkins-ci.org/display/JENKINS/Working+With+the+Pipeline+Jenkins+Plugin).

## Examples
The examples below are meant to help you get started using the Artifactory DSL in your Pipeline scripts.
Follow the below steps to run the examples.

### Step 1 - Configure Artifactory Server for the Examples
All examples use an Artifactory server defined in Manage Jenkins, Configure System.
The server is retrieved by the examples as follows:
```
def server = Artifactory.server SERVER_ID
```
To set server ID for examples, follow these steps:
* Find or configure an Artifactory server in Jenkins through Manage Jenkins, Configure System.
* In the configuration of the Jenkins job that runs the example, check the *This project is parameterized* option.
* Click *Add Parameter* and then select *String Parameter*.
* Set the *Name* as *SERVER_ID* and the *Default Value* as the Artifactory Server ID configured in *Manage Jenkins*.

### Step 2 - Complete the Job Configuration

You cancomplete the job configuration by following one of the two methods described below.
#### Method 1:
In your Jenkins job configuration, set *Definition* to "Pipeline script",
and then copy the content of the example's Jenkinsfile into the *Script* text-area.
#### Method 2:
In your Jenkins job configuration, set the following:
* Set *Definition* to "Pipeline script from SCM".
* Set *SCM* to *Git*.
* Set *Repository URL* to *https://github.com/JFrog/project-examples.git*
* Set *Script Path* to the relative path to the example's Jenkinsfile. For example, for the below *props-example*, set *Script Path* to *jenkins-examples/pipeline-examples/props-example/Jenkinsfile* 

### Available Examples
Here are the available examples.
* The [props-example](props-example) downloads and uploads files to Artifactory with properties. The props-example also uses a placeholder when uploading.
* The [props-single-file-example](props-single-file-example) is the same as the [props-example](props-example), but has the specs embedded inside the Groovy script.
* The [promotion-example](promotion-example) demonstrates how to promote a build in Artifactory.
* The [vars-build-retention-example](vars-build-retention-example) demonstrates capturing environment variables and build retention in Artifactory.
* The [aql-example](aql-example) uses a Download Spec which includes [AQL](https://www.jfrog.com/confluence/display/RTF/Artifactory+Query+Language) instead of a wildcard pattern.
* The [maven-example](maven-example) resolves dependencies, deploys artifacts and publishes build-info to Artifactory for a Maven build.
* The [maven-deploy-example](maven-deploy-example) demonstrates how to defer the build artifacts deployment to a separate stage.
* The [gradle-example-ci-server](gradle-example-ci-server) resolves dependencies, deploys artifacts and publishes build-info to Artifactory for a Gradle build. Unlike the [gradle-example](gradle-example), this examples assumes that the Gradle Artifactory Plugin in not applied to the Gradle build script.
* The [gradle-example](gradle-example) resolves dependencies, deploys artifacts and publishes build-info to Artifactory for a Gradle build. Unlike the [gradle-example-ci-server](gradle-example-ci-server), this examples assumes that the Gradle Artifactory Plugin in already applied in the Gradle build script.
* The [gradle-deploy-example](gradle-deploy-example) demonstrates how to defer the build artifacts deployment to a separate stage.
* The [declarative-example](declarative-example) demonstrates how to download, upload and publish build-info to Artifactory using a Declarative Pipeline script.
* The [exclude-patterns-download-example](exclude-patterns-download-example) demonstrates how to exclude certain files while downloading.
* The [exclude-patterns-upload-example](exclude-patterns-upload-example) demonstrates how to exclude certain files while uploading.
* The [maven-container-example](maven-container-example) demonstrates how to run Maven in a Docker container.
* The [gradle-container-example](gradle-container-example) demonstrates how to run Gradle in a Docker container.

Learn more about [working with pipeline jobs in Jenkins](https://www.jfrog.com/confluence/display/RTF/Working+With+Pipeline+Jobs+in+Jenkins) and the benefits of [Artifactory’s integration with Jenkins CI](https://jfrog.com/integration/jenkins-ci/).