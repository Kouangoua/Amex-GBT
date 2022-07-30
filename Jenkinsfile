pipeline{
    agent any

    tools {
         maven 'maven3.8.4'
    }

    stages{
        stage('checkout'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*']], extensions: [], userRemoteConfigs: [[credentialsId: '', url: 'https://github.com/Kouangoua/Amex-GBT.git']]])
            }
        }
        stage('build'){
            steps{
               sh 'mvn package'
            }
        }
        post {
            success {
                echo 'test'
            }
        }        
    }
}