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
                git branch: 'main', credentialsId: 'github', url: 
            }
        }
    }

}
