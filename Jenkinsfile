pipeline{
    agent any

    stages{

        stage('sonar quality check'){

            agent{
                docker{
                    image 'maven'
                }
            }

            steps{

                script{
                    withSonarQubeEnv(credentialsId: 'jenkins') {

                        sh 'mvn clean package sonar:sonar'
                }
                    
                }
            }
           }
        
        stage('Quality Gate status'){
            steps{
                script{
                    waitForQualityGate abortPipeline: false, credentialsId: 'jenkins'
                }
            }
        }
        
        stage('Docker build & push to nexus'){
            steps{
                script{
                    
          }
       }
