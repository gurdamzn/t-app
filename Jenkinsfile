pipeline {
    agent any
    stages {
        stage('Upgrading pip, wheel and setuptools') {
            agent {
                docker {
                    image 'circleci/python:3.6.2-stretch-browsers'
                    args ''
                    reuseNode true
                }
            }
            steps {
                sh 'echo "Creating virtualenv"'
                sh 'python3 -m venv venv'

                sh 'echo "Activating virtualenv"'
                sh '. venv/bin/activate'

                sh 'echo "Installing dependenices"'
                sh 'pip install -r requirements/dev.txt'
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
