pipeline {
    agent any
    environment {
        START_TIME = date
        buildUser = ''
      }
    stages {
        stage('First Test') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Second Test') {
            steps {
                echo 'START_TIME: ${START_TIME} test github commit trigger again'
            }
        }
        stage('Get User') {
            steps {
                script {
                    // Execute the shell command and store the output in a Groovy variable
                    def buildUser = sh(script: 'whoami', returnStdout: true).trim()

                    // Use the variable later in the pipeline
                    echo "The build is running as: ${buildUser}"
                }
            }
        }
        stage('Last test') {
            steps {
                echo "START_TIME: ${START_TIME} test github commit trigger again: ${buildUser}"
            }
        }
    }
}
