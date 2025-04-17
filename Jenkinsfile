pipeline{
    agent any

    tools{
        jdk "java-11"
        maven "maven"
    }
    
    stages{
         stage('Git-Checkout'){
        
         steps{
             git branch: 'shannu', url: 'https://github.com/shannu0188/first-project.git'
         }

         }
         stage('compile'){
                steps{
                    sh 'mvn compile'
                }
        }
        stage('package'){
            steps{
                sh 'mvn clean install'
            }
        }

        stage('docker-build'){
                steps{
                   sh 'docker build -t shannu888/app .'
                }
        }
        stage('containerization'){
                steps{
                   sh 'docker run -it -d --name c1 -p 9001:80 shannu888/app'
                }
        }
    }
}
