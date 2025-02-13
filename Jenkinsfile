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

       
    }
}
