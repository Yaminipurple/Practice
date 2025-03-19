pipeline {
    agent any  // Runs on any available agent

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/your-repo/sample-project.git'
            }
        }

        stage('Build') {
            steps {
                sh 'echo "Building the project..."'
                sh 'mvn clean package'  // Example for Java projects
            }
        }

        stage('Test') {
            steps {
                sh 'echo "Running tests..."'
                sh 'mvn test'  // Replace with actual test commands
            }
        }

        stage('Deploy') {
            steps {
                sh 'echo "Deploying application..."'
                // Replace with actual deployment commands
                sh 'scp target/*.jar user@server:/deploy/path/'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed! Check logs for errors.'
        }
    }
}
