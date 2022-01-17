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
    
    stage('Docker image build') {
      steps {
        sh 'docker images rmi*' 
        sh 'docker build -t myapp .'
      }
    }

    stage('deploy') {
      steps {

        sh 'sudo cp -r /var/lib/jenkins/workspace/Application/webapp/target/webapp.war /usr/share/tomcat/webapps/'

      }
    }

    stage('upload image to dockerhub') {
      steps {

        sh 'docker image tag myapp shivampandeyaps/myapp_v2.0'
        sh 'docker push shivampandeyaps/myapp_v2.0'

      }
    }

  }

}
