//@Library("shared-library") _
pipeline {

  agent any

  tools {
    // Install the Maven version configured.
    maven "maven3"
  }

  stages {

    stage('build') {
      steps {
        sh 'mvn clean install'
      }
    }

    stage('deploy') {
      steps {

        sh 'sudo cp -r /var/lib/jenkins/workspace/Application/webapp/target/webapp.war /usr/share/tomcat/webapps/'

      }
    }

  }

}
