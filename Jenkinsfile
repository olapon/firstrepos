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
                 withCredentials([usernamePassword(credentialsId: 'server-credentials', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
  // available as an env variable, but will be masked if you try to print it out any which way
  // note: single quotes prevent Groovy interpolation; expansion is by Bourne Shell, which is what you want
  sh 'echo $PASSWORD'
  // also available as a Groovy variable
  echo USERNAME
  // or inside double quotes for string interpolation
  echo "username is $USERNAME"
}
                 echo env.JENKINS_HOME
                 echo "New Version is : ${NEW_VERSION}"
                 //echo "Credentials is : ${SERVER_CREDENTIALS}"
                
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

