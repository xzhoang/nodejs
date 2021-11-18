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
         stage('Install pm2') {
            steps {
                echo 'Installing pm2...'
                sh 'npm install pm2 -g'
            }
        }
        stage('Install curl') {        
            steps {
                echo 'Installing curl...'
                sh 'apt install curl -y'
            }
        }
        stage('Run nodejs app') {
            steps {
                echo 'Starting application...'
                sh 'pm2 start bin/www'
            }
        }
	stage('Test nodejs app') {
            steps {
                echo 'Accesscing application...'
                sh "curl 'http://127.0.0.1:3000' "
            }
        }
        
    }
 }
