#!/usr/bin/env groovy

pipeline {

    agent {
        docker {
            image 'node:14'
            args "-u root -p 3000:3000"
        }
    }

    stages {
        stage('Build npm install') {
            steps {
                echo 'Installing Dependencies...'
                sh 'npm install'
            }
        }
        stage('Run nodejs app') {
            steps {
                echo 'Starting application...'
                #sh 'node bin/www'
                sh 'pm2 start bin/www'
            }
        }

        
    }
 }
