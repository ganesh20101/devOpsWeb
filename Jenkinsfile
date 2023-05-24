pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        // Checkout the source code from the repository
        git branch: 'main', credentialsId: '123', url: 'https://github.com/ganesh20101/devOpsWeb.git'
      }
    }

    stage('Build') {
      steps {
        // Build your application
        // (e.g., compile, run tests, package as a WAR file)
        sh 'mvn clean package'
      }
    }

    stage('Deploy to Tomcat') {
      steps {
        // Copy the WAR file to the Tomcat webapps directory
        deploy adapters: [tomcat9(credentialsId: '90b81f7f-735b-4330-8aee-f24f94bd4200', path: '', url: 'http://13.211.71.182:8080/')], contextPath: null, war: '**/* .war'
      }
    }
  }
}
