pipeline {

    agent any

    stages {

        stage('Clone') {

            steps {

                git branch: 'main',
                    url: 'https://github.com/Seshaveni123/project4.git'

            }

        }

        stage('Build Image') {

            steps {

                sh 'docker build -t project4 .'

            }

        }

        stage('Deploy') {

            steps {

                sh 'docker stop nginx-cont || true'
                sh 'docker rm nginx-cont || true'

                sh 'docker run -d -p 8080:80 --name nginx-cont project4'

            }

        }

    }

}
