pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                build 'PES1UG21CS523-1'
                sh 'g++ new.cpp -o output'
            }
        }

        stage('Test') {
            steps {
                sh './nonexistent-script'  // Intentionally introduce an error
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy'
            }
        }
    }

    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
