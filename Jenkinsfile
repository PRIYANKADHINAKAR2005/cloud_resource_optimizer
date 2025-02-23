pipeline {
    agent any

    environment {
        GOOGLE_APPLICATION_CREDENTIALS = credentials('GCP_CREDENTIALS') // Uses your GCP JSON key
    }

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/PRIYANKADHINAKAR2005/cloud_resource_optimizer.git' // Change to your repo URL
            }
        }

        stage('Fetch Cloud Costs') {
            steps {
                script {
                    def result = sh(script: """
                        gcloud auth activate-service-account --key-file=\$GOOGLE_APPLICATION_CREDENTIALS
                        gcloud beta billing projects list
                    """, returnStdout: true).trim()
                    echo "Billing Data: \\n${result}"
                }
            }
        }
    }
}
