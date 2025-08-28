pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout your source code from SCM (Git)
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building the Java app with Maven...'
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                echo 'Running unit tests with Maven...'
                // Tests run as part of mvn install, but you can run separately if needed
                sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                // Add your deployment commands here
                // e.g., copying jar to server, running deploy scripts, etc.
                // sh 'scp target/myapp.jar user@server:/path/to/deploy'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Check logs.'
        }
    }
}
