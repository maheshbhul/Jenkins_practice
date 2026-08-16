// pipeline{
//     agent any
//     tools{
//         maven 'Maven-3'
//     }
//     stages{
//         stage('Checkout'){
//             steps{
//                 echo 'Source code checkout complicated'
//             }
//         }
//         stage('Build'){
//             steps{
//                 sh 'mvn clean compile'

//             }
//         }
//         stage('Test'){
//             steps{
//                 sh 'mvn test'
//             }
//         }
//         stage('Package'){
//             steps{
//                 sh 'mvn package -DskipTests'
//             }

//         }
//     }
//     post{
//         success{
//                 echo 'Pipeline completed successfully!'

//         }
//         failure{
//                 echo 'pipeline failed!'
//         }
//         always{
//                 echo 'Pipeline execution completed'
//         }
//     }
// }


pipeline{
    agent any
    tools{
        maven 'Maven-3'
    }

    stages{
        stage('Checkout'){
            steps{
                echo 'Source code checkout completed'
            }
        }
        stage('Environment Info'){
            steps{
                echo'Job Name: ${env.JOB_NAME}'
                echo'Build number: ${env.BUILD_NUMBER}'
                echo'Workspace: ${env.WORKSPACE}'
                echo 'Build ID: ${env.BUILD_ID}'
            }
        }
        stage('Build'){
            steps{
                sh 'mvn clean compile'
            }
        }
        stage('Test'){
            steps{
                sh 'mvn test'
            }
        }
        stage('Package'){
            steps{
                sh 'mvn package -DskipTests'
            }
        }
    post{
        success{
            echo 'Pipeline completed successfully!'
        }
        failure{
            echo 'Pipeline failed!'
        }
        always{
            echo 'Pipeline execution complted'
        }
     }   
    }
}