pipeline {
    agent any
 
    stages {
        stage('Git') {
            steps {
                echo '> Checking out the Git version control ...'
                checkout scm
            }
        }
        stage('Build') {
            steps {
                echo '> Building the docker containers ...'
                sh 'make -sC docker build'
            }
        }
        stage('Test') {
            steps {
                echo '> Running the application tests ...'
                sh 'make -sC docker test'
            }
        }
        stage('Destroy') {
            steps {
                echo '> Destroying the docker artifacts ...'
                sh 'make -sC docker destroy'
            }
        }
    }
}
