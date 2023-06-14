pipeline {
    agent any
    
    stages {
        stage('SonarQube Connection Check') {
            steps {
                script {
                    def scannerHome = tool 'karan-sonar';
                    //withCredentials([usernamePassword(credentialsId: 'sonarqube-credentials', usernameVariable: 'SONAR_LOGIN', passwordVariable: 'SONAR_PASSWORD')]) {
                        withSonarQubeEnv('sonarqube-server', -Dsonar.login=jenkins, -Dsonar.password=admin){
                            sh "${scannerHome}/bin/sonar-scanner"
                 
                    }
                }
            }
        }
    }
}
