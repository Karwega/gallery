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
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}