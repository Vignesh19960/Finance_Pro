pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https://github.com/Vignesh19960/Finance_Pro/'
                 echo 'github url checkout'
            }
        }
        stage('codecompile with vignesh'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('codetesting with vignesh'){
            steps{
                sh 'mvn test'
            }
        }
        stage('QA with vignesh'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package with vignesh'){
            steps{
                sh 'mvn package'
            }
        }
        stage('run dockerfile'){
          steps{
               sh 'docker build -t myimg .'
           }
         }
        stage('port expose'){
            steps{
                sh 'docker run -dt -p 8091:8091 --name c000 myimg'
            }
        }   
    }
}
