pipeline {
    agent any

    environment {
        GOOGLE_APPLICATION_CREDENTIALS = credentials('GCP_CREDENTIALS') // Uses your GCP JSON key
    }

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/your-username/your-repo.git' // Change to your repo URL
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip install -r requirements.txt' // Install Python dependencies
            }
        }

        stage('Fetch Billing Data from GCP') {
            steps {
                sh 'python fetch_billing_data.py' // Runs script to fetch billing data
            }
        }

        stage('Run ML Model for Cost Optimization') {
            steps {
                sh 'python optimize_costs.py' // Runs ML model for cost prediction
            }
        }

        stage('Deploy Optimized Results') {
            steps {
                sh 'python deploy_results.py' // (Optional) Deploy results to a dashboard
            }
        }
    }
}
