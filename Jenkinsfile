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
        
        
//          stage('docker container instance') {
//             steps {
//                 script{
//                  sh 'sudo docker build -t customimage .'
//                 }
//             }
//         }

        stage('deploy') {
            steps {

                sh 'sudo cp -r /var/lib/jenkins/workspace/Application/webapp/target/webapp.war /usr/share/tomcat/webapps/'
             



            }
        }
        stage('Upload to nexus'){
            steps{
                nexusArtifactUploader artifacts: [[artifactId: 'maven-project', classifier: '', file: '/var/lib/jenkins/workspace/Application/webapp/target/webapp.war', type: 'war']], credentialsId: '3f9a696a-c0ae-417b-a268-2d397cb20948', groupId: 'com.example.maven-project', nexusUrl: '13.127.162.77:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'http://13.127.162.77:8081/repository/Application/', version: '1.0-SNAPSHOT'      
            }
        }
    
    
    }




}
