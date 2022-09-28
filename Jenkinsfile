pipeline{
    agent any

    stages{
       
       stage('Build'){
            steps{
                sh 'mvn clean install'
                sh 'mvn clean package'
            }
         }
        stage('SonarQube analysis') {
    def scannerHome = tool 'sonarqubescanner-4.7.0';
        steps{
        withSonarQubeEnv('sonarqube-9.4') { 
        // If you have configured more than one global server connection, you can specify its name
//      sh "${scannerHome}/bin/sonar-scanner"
        sh "mvn sonar:sonar"
    }
        }
        }
       
    }
}
