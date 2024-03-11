pipeline {
    agent any

    environment {
        // Define environment variables if needed
    }

    stages {
        stage('Clone Repository') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    // Assuming Python and pip are installed
                    sh 'python -m pip install -r requirements.txt'
                }
            }
        }

        stage('Execute Test') {
            steps {
                script {
                    sh 'python test.py'
                }
            }
        }

        stage('Deploying') {
            steps {
                script {
                    if (env.BRANCH_NAME == 'main') {
                        echo 'Deploying to production'
                    } else {
                        echo 'Deploying to UAT'
                    }
                }
            }
        }
    }
}
