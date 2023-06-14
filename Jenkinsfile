pipeline {
    agent any
    
    stages {
        stage('SonarQube Connection Check') {
            steps {
                script {
                    def scannerHome = tool 'karan-sonar';
                    withSonarQubeEnv('sonarqube-server', credentialsId:'squ_21ffec8a6409548110e67d6fbecff79006e0bcb'){
                        sh "${scannerHome}/bin/sonar-scanner"
                    }
                }
            }
        }
    }
}
