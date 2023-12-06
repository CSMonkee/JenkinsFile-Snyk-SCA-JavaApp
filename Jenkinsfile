// Jenkins pipeline definition
pipeline {

  // Run on any available agent
  agent any 

  stages {

    // Checkout code from Git repository
    stage('Checkout') {
      steps {
        git 'https://github.com/CSMonkee/WebGoat.git'
      }
    }
    
    // Build the Java application with Maven
    stage('Build') { 
      steps {
        sh 'mvn clean install' // run mvn clean install
      }
    }
    
    // Run unit tests with Maven
    stage('Test') {
      steps {
        sh 'mvn test' // run mvn test
      }
    }
    
    // Run SCA scan with Snyk 
    stage('SCA Scan') {
      steps {
      
        // Get Snyk API token from Jenkins credentials
        withCredentials([string(credentialsId: 'SNYK_TOKEN', variable: 'SNYK_TOKEN')]) {
        
          // Authenticate with Snyk  
          sh 'snyk auth $SNYK_TOKEN'
          
          // Run Snyk test and fail build if vulnerabilities found
          sh 'snyk test --fail-on=upgradable --project-name=my-java-app'
        }
      }
    }
  }
}
