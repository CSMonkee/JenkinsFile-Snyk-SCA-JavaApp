# ![My Skills](https://skillicons.dev/icons?i=jenkins,maven,vscode,java,github) <img src ="https://github.com/DrllSGT/JenkinsFile-Snyk-SCA-JavaApp/assets/52445175/ff84aab7-372e-4113-9049-fe7dbe4abcc7" width=48>
# JenkinsFile for Snyk SCA on Java App

As a DevSecOps engineer I have been tasked with creating a Jenkinsfile for performing SCA scan on a Java web application using Snyk. The Jenkinsfile should include the following stages:

- **Checkout:** Checkout the source code from a Git repository "https://github.com/your-repo/your-node-app.git".
- **Build:** Build the Java application using the "mvn install" command.
- **Test:** Run unit tests on the Node.js application using the "mvn test" command.
- **SCA scan:** Run SCA scan using Snyk. Credentials are stored in Jenkins credential manager. Use "SNYK_TOKEN" as credentialsId and variable name for passing the credentials to the stage. Make sure that Snyk FAILS the build if security vulnerabilities are identified in third party libraries.


This Jenkinsfile:

- Checks out code from the git repo
- Builds the Java app with Maven
- Runs unit tests
- Authenticates with Snyk using credentials from Jenkins
- Runs Snyk test and fails the build if vulnerabilities are found
