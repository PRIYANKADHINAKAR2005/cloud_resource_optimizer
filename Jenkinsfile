pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/PRIYANKADHINAKAR2005/cloud_resource_optimizer.git'
            }
        }
        stage('Build') {
            steps {
                echo 'Building the project'
                // Add your build steps here, e.g., npm install
            }
        }
    }
}
