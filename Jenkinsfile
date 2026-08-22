pipeline {
    agent any

    tools {
        maven 'Maven-3'
    }

    stages {

        stage('Checkout') {
            steps {
                echo 'Source code checkout completed'
            }
        }

        stage('Environment Info') {
            steps {
                echo "Job Name: ${env.JOB_NAME}"
                echo "Build Number: ${env.BUILD_NUMBER}"
                echo "Workspace: ${env.WORKSPACE}"
                echo "Build ID: ${env.BUILD_ID}"
            }
        }

        stage('Credentials Test') {
            steps {
                withCredentials([
                        usernamePassword(
                                credentialsId: 'demo-credential',
                                usernameVariable: 'USERNAME',
                                passwordVariable: 'PASSWORD'
                        )
                ]) {
                    sh 'echo "username is: $USERNAME"'
                }
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                sh 'mvn package -DskipTests'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }

        failure {
            echo 'Pipeline failed!'
        }

        always {
            echo 'Pipeline execution completed.'
        }
    }
}