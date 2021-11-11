#!/usr/bin/env groovy

pipeline {

    agent {
        docker {
            image 'node'
            args '-u root'
        }
    }

    stages {
        stage('Build') {
            steps {
                echo 'Installing Dependencies...'
                sh 'npm install'
            }
        }
        stage('Run') {
            steps {
                echo 'Starting application...'
                sh 'node bin/www'
            }
        }

        }
    }
 }
