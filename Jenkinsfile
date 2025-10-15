pipeline {
    
    agent any

    stages {
        stage('Build') {
            steps {
               echo "Building application..."
            }
        }

        stage('Test') {
            steps {
                echo "Runnig tests"
            }
        }
    }
   post {
        success {
            emailext (
                to: 'divyatest2302@gmail.com',
                subject: "SUCCESS: Job '${env.JOB_NAME}' #${env.BUILD_NUMBER}",
                body: """
                <h2>Build Successful!</h2>
                <p>Job: ${env.JOB_NAME}</p>
                <p>Build Number: ${env.BUILD_NUMBER}</p>
                <p>Check details: <a href="${env.BUILD_URL}">${env.BUILD_URL}</a></p>
                """,
                mimeType: 'text/html'
            )
        }

        failure {
            emailext (
                to: 'divyatest2302@gmail.com',
                subject: " FAILURE: Job '${env.JOB_NAME}' #${env.BUILD_NUMBER}",
                body: """
                <h2>Build Failed!</h2>
                <p>Job: ${env.JOB_NAME}</p>
                <p>Build Number: ${env.BUILD_NUMBER}</p>
                <p>Check console log: <a href="${env.BUILD_URL}">${env.BUILD_URL}</a></p>
                """,
                mimeType: 'text/html'
            )
        }
    }
}