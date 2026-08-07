pipeline {
    agent

    tools {
            maven 'Maven-3'
        }


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