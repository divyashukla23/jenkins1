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
    
    post{
        success{
            emailText {
                to: 'divyatest2302@gmail.com',
                subject: "SUCCESS '${env.JOB_NAME}' #${env.BUILD_NUMBER}",
                body: """
                <h3> BUILD SUCESSFUL! </h3>
                <p>Job: ${env.JOB_NAME} </p>
                <p> Build number: ${env.BUILD_NUMBER} </p>
                mimeType: 'text/html'
                """,
            }
        }
    }
}