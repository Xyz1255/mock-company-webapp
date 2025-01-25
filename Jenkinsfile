pipeline {
  /*
   * TODO: Implement pipeline stages/steps
   *   See documentation: https://www.jenkins.io/doc/book/pipeline/syntax/#stages
   */

   pipeline {
    agent any // This specifies that the pipeline can run on any available agent

    environment {
        // Define environment variables if needed
        // Example: JAVA_HOME = '/path/to/java'
    }

    stages {
        // Stage for checking out the code from GitHub
        stage('Checkout') {
            steps {
                // Checkout the latest code from the repository
                git 'https://github.com/YourGitHubUsername/mock-company-webapp.git'
            }
        }

        // Stage for building the project
        stage('Build') {
            steps {
                // Run the Gradle build command
                sh './gradlew assemble' // Executes the assemble task
            }
        }

        // Stage for running tests
        stage('Test') {
            steps {
                // Run the Gradle test command
                sh './gradlew test' // Executes the test task
            }
        }
    }

    post {
        // Post actions to handle build status
        success {
            echo 'Build and tests passed successfully.'
        }
        failure {
            echo 'Build or tests failed.'
        }
    }
}

}
