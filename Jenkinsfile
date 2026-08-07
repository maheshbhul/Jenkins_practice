pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                echo 'Project already cloned by Jenkins'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

    }
}