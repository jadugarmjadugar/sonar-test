pipeline{
    agent any
    stages{    
        stage('SCM') {
            steps{
                checkout([$class: 'GitSCM',
                branches: [[name: 'main']],  
                extensions: [[$class: 'CleanCheckout']],
                userRemoteConfigs: [[url: 'https://github.com/edureka27/webapp.git']]])
            }
        }
        stage('SonarQube Analysis') {
            steps{
                script{
                    def mvn = tool 'Maven'
                    withSonarQubeEnv(installationName: 'sonarqube-server') {
                        sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=hello -Dsonar.projectName='hello'"
                    }
                }    
            }    
        }
    } 
}
