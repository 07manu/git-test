pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo '🔧 Building the application...'
            }
        }

        stage('Tests (Only on master)') {
            when {
                branch 'master'
            }
            parallel {
                stage('Unit Tests') {
                    steps {
                        echo '✅ Running Unit Tests (on master only)'
                    }
                }

                stage('Integration Tests') {
                    steps {
                        echo '✅ Running Integration Tests (on master only)'
                    }
                }
            }
        }

        stage('Deploy') {
            steps {
                echo '🚀 Deploying the application...'
            }
        }
    }

    post {
        success {
            echo '🎉 Pipeline finished successfully!'
        }
        failure {
            echo '❌ Pipeline failed!'
        }
    }
}
