pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https://github.com/pshakeerbasha/Healthcare-project/'
                 echo 'github url checkout'
            }
        }
        stage('codecompile with shakeer'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('codetesting with shakeer'){
            steps{
                sh 'mvn test'
            }
        }
        stage('qa with shakeer'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package with shakeer'){
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
                sh 'docker run -dt -p 8091:8091 --name c001 myimg'
            }
        }
    }
}

