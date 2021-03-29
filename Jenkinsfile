pipeline{
    //Directives
    agent any
    tools {
        maven 'maven'
    }

    stages {
        // Specify various stage with in stages

        // stage 1. Build
        stage ('Build'){
            steps {
                sh 'mvn clean install package'
            }
        }

        // Stage2 : Testing
        stage ('Test'){
            steps {
                echo ' testing......'

            }
        }

        stage ('Publish to Nexus') {
            steps {
                nexusArtifactUploader artifacts: [[artifactId: 'SrinathDevOpsLab', classifier: '', file: 'target/SrinathDevOpsLab-0.0.8-SNAPSHOT.war', type: 'war']], credentialsId: 'a9879a3a-bc92-42a8-8331-17b20a4a85fb', groupId: 'com.vinaysdevopslab', nexusUrl: 'http://3.139.86.194:8081/', nexusVersion: 'nexus3', protocol: 'http', repository: 'SrinathsDevOpsLab-SNAPSHOT', version: '0.0.8-SNAPSHOT'
            }
        }
        // Stage3 : Testing
        stage ('Deploy'){
            steps {
                echo ' deploying......'

            }
        }


        // Stage3 : Publish the source code to Sonarqube
       // stage ('Sonarqube Analysis'){
        //    steps {
        //        echo ' Source code published to Sonarqube for SCA......'
         //       withSonarQubeEnv('sonarqube'){ // You can override the credential to be used
          //           sh 'mvn sonar:sonar'
         //       }

          //  }
       // }

        
        
    }

}