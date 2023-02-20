pipeline {
    agent any
    environment {
        NEW_VERSION = "5.23.100"
    }

    stages {
        stage("Build") {
            steps {
                echo "Building the application"
            }
        }
         stage("Test") {
             steps {
                echo "Testing the application"
                 echo env.JENKINS_HOME
                 echo "New Version is : ${NEW_VERSION}"
                
            }
        }
        stage("Deploy") {
            steps {
                echo "Deploying the application"
            }
        }
    }
    post {
        always {
            echo "Always executed"
        }
        failure {
            echo "execute ONLy on Failure"
        }
    }
}
