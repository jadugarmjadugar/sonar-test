pipeline {
    agent any
    
    stages {
        stage('SonarQube Connection Check') {
            steps {
                script {
                    def scannerHome = tool 'karan-sonar';
                    withSonarQubeEnv('sonarqube-server'){
                        sh "${scannerHome}/bin/sonar-scanner -Dsonar.login=jenkins -Dsonar.password=admin"
                    }
                }
            }
        }
    }
}
