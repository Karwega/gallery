pipeline {
    agent any

    stages {
        stage('clone repository') {
      steps { 
        git 'https://github.com/Karwega/gallery.git/'
      }
    }
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing....'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
        stage('Slack notification') {
            steps {
                slackSend channel: '#karwega_ip1', message: "Successfully deployed build id: {BUILD_ID}"
            }
        }
    }
}