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
                sh 'npm test'
            }
            post{
                failure{
                    mail bcc: '', body: 'We hate to be the bearer of bad news but the build on your app has failed.', cc: '', from: '', replyTo: '', subject: 'Build Status: Failure', to: 'stephanie.kibet@student.moringaschool.com, stephkiby@gmail.com, '
                    }
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
        stage('Slack notification') {
            steps {
                slackSend channel: '#karwega_ip1', message: "Successfully deployed build id: ${BUILD_ID}"
            }
        }
    }
}