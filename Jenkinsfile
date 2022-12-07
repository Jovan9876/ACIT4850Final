// Jovan Sandhu (A01201367)
// December 7, 2022
// ACIT4850 Final Exam pipeline
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Jovan Sandhu (A01201367) GROUP 39'
                echo 'Installing the Requirements...'
                sh 'pip install -r requirements.txt'
                echo 'Requirement completed'
            }
        }
        stage('Code Quality') {
            steps {
                script {
                    sh "pylint-fail-under --fail_under 5.0 *.py"
                }
            }
        }
        stage('Code Quantity') {
            steps {
                sh 'ls *.py | wc -l'
            }
        }
        stage('Test Program') {
            steps {
                sh 'python3 test_book_manager.py'
            }
        }
        stage('Package') {
            steps {
                sh "zip -r output.zip ."
            }
            post {
                always {
                    archiveArtifacts 'output.zip'
                }
            }
        }
    }
}
