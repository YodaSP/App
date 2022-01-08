//@Library("shared-library") _
pipeline {

    agent any
    
    tools {
        // Install the Maven version configured.
        maven "maven3.8.4"
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

//         stage('deploy') {
//             steps {

//                 sh 'sudo cp -r /var/lib/jenkins/workspace/My_App2/webapp/target/webapp.war /opt/apache-tomcat-8.5.73/webapps/'


//             }
//         }
    }




}
