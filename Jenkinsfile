pipeline {
    agent any
    
    stages {
        stage('SonarQube Connection Check') {
            steps {
                script {
                    def scannerHome = tool 'karan-sonar';
                    //withCredentials([usernamePassword(credentialsId: 'sonarqube-credentials', usernameVariable: 'SONAR_LOGIN', passwordVariable: 'SONAR_PASSWORD')]) {
                        withSonarQubeEnv('sonarqube-server'){
                            sh "${scannerHome}/bin/sonar-scanner -Dsonar.login=squ_21ffec8a6409548110e67d6fbecff79006e0bcb"
                 
                    }
                }
            }
        }
    }
}
