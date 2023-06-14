pipeline {
    agent any
    
    stages {
        stage('SonarQube Connection Check') {
            steps {
                script {
                    def scannerHome = tool 'karan-sonar';
                    //withCredentials([usernamePassword(credentialsId: 'sonarqube-credentials', usernameVariable: 'SONAR_LOGIN', passwordVariable: 'SONAR_PASSWORD')]) {
                        withSonarQubeEnv('sonarqube-server'){
                            //sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=karan -Dsonar.projectName='karan'"
                            sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectKey=karan -Dsonar.projectName='karan'"
                 
                    }
                }
            }
        }
    }
}
