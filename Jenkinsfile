pipeline {
    agent any

    parameters {
        choice(
            name: 'ENVIRONMENT',
            choices: ['DEV', 'QA', 'UAT', 'PROD'],
            description: 'Select deployment environment'
        )
    }

    tools {
        maven 'Maven'
    }

    stages {

        stage('Environment') {
            steps {
                echo "Deploying to ${params.ENVIRONMENT}"
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
    }

    post {
        success {
            echo 'Build Successful'
        }

        failure {
            echo 'Build Failed'
        }
    }
}