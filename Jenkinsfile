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
                 nexusArtifactUploader artifacts: [[artifactId: 'maven-project', classifier: 'target', file: 'Maven Project-1.0.0.war', type: 'war']], credentialsId: '', groupId: 'com.example.maven-project', nexusUrl: '3.108.249.210', nexusVersion: 'nexus3', protocol: 'http', repository: 'http://3.108.249.210:8081/repository/Application/', version: '1.0-SNAPSHOT'      
            }
        }
    
    
    }




}
