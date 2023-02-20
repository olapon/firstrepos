pipeline {
    agent any

    stages {
        stage("Build") {
            steps {
                echo "Building the application"
            }
        }
         stage("Test") {
             when {
                 expression {
                     BRANCH_NAME == "dev"
                 }
             } 
            steps {
                echo "Testing the application"
                
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
