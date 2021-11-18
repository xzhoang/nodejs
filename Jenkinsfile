#!/usr/bin/env groovy

pipeline {

    agent {
        docker {
            image 'node:14'
            args "-u root -d -p 3000:3000"
        }
    }

    stages {
        stage('Build npm install') {
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
