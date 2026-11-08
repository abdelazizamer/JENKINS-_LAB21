@Library('ivolve-lab22') _

pipeline {
    agent { label 'lab22-agent' }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build App') {
            steps {
                BuildApp()
            }
        }

        stage('Build Image, Scan and Push') {
            steps {
                BuildImage()
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                DeployOnK8s()
            }
        }
    }

    post {
        success {
            echo 'Lab 22 pipeline completed successfully.'
        }
        failure {
            echo 'Lab 22 pipeline failed. Check the Console Output.'
        }
    }
}
