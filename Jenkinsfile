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
        stage('upload'){
            steps{
               s3Upload(file:'jbHelloWorldMaven020', bucket:'AmexGBT', path:'target/jb-hello-world-maven-0.2.0.ja')
            }
        }
    }
}