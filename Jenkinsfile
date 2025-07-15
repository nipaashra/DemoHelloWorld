pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Running build step...'
            }
        }

        stage('Test') {
            steps {
                echo 'Running test step...'
            }
        }
    }

    post {
        success {
            echo 'Sending build info to Jira'
            jiraSendBuildInfo site: 'nipaashra.atlassian.net'
        }
        failure {
            echo 'Build failed, still sending info to Jira'
            jiraSendBuildInfo site: 'nipaashra.atlassian.net'
        }
    }
}
