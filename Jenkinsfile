pipeline {
    agent { label 'Jenkins-Agent'}
    
    tools {
        jdk 'Java21'
        maven 'Maven'
    }

    stages {
        stage('Workspace Cleanup'){
            steps{
                cleanWs()
            }
        }

        stage('Checkout from SCM'){
            steps{
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/Shubhamsoni024/register-app.git'
            }
        }

        stage('Build Application'){
            steps{
                sh "mvn clean package"
            }
        }

        stage('Test Application'){
            steps{
                sh "mvn test"
            }
        }
        
        stage('SonarQube Analysis'){
            steps{
                withSonarQubeEnv(credentialsId: 'jenkins-sonarqube-token'){
                    sh "mvn sonar:sonar"
                }
            }
        }

    }
}
