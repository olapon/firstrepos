pipeline {
    agent any
    environment {
        NEW_VERSION = "5.23.100"
        SERVER_CREDENTIALS = credentials("server-credentials")
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
                 echo "Credentials is : ${SERVER_CREDENTIALS}"
                
            }
        }
        stage("Deploy") {
            steps {
                echo "Deploying the application"
                withCredentials([
                    usernamPassword(credentials: 'server-credentials', usernameVariable: USER , passwordVariable: PASSV)
                ]){
                  echo "Credentials is : ${USER}"
                echo "Credentials is : ${PASSV}"
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
