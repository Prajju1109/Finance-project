pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https://github.com/Prajju1109/Finance-project.git'
                 echo 'github url checkout'
            }
        }
        stage('codecompile with prajju'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('codetesting with prajju'){
            steps{
                sh 'mvn test'
            }
        }
        stage('qa with prajju'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package with prajju'){
            steps{
                sh 'mvn package'
            }
        }
        stage('run dockerfile'){
          steps{
               sh 'docker build -t myimg1 .'
           }
         }
        stage('port expose'){
            steps{
                sh 'docker run -dt -p 8091:8091 --name c001 myimg1'
            }
        }   
    }
}
