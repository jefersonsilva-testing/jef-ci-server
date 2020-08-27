pipeline {
    agent{
        docker {
            // image 'python:3.7.7-stretch'    --- essa imagem não tinha o chromedriver configurado e troquei para a do QA Ninja
            // alterei para utilizar a mesma imagem docker utilizada no curso da QA Ninja 2020
            image 'qaninja/python-wd'
            args '--network=skynet'
            }
    }

    stages {
        stage('Build') {
            steps {
                sh 'pip install robotframework'
                sh 'pip install robotframework-requests'
                sh 'pip install robotframework-jsonlibrary'
                sh 'pip install robotframework-seleniumlibrary'
                sh 'pip install psycopg2'
                sh 'pip install requests'
                sh 'pip install webdrivermanager'

            }
        }
        stage('Testing') {
                steps {
                // sh 'robot title.robot' -- ajustando para fazer login ao cotaz
                   sh 'robot luc.robot'
                      }    
            }
        }
    }