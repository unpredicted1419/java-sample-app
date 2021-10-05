pipeline {
    agent any
    environment {
        PRD = "PROD"
        DEV = "DEV"
        UAT = "ACC"
    }
    stages {
        
        stage ("Build Source Code"){
            steps {
                script{
                    sh """
                        mvn clean install
                    """
                }
            }
        }
        stage ("Code Analysis"){
            steps {
                script {
                    sh "/opt/sonar/bin/sonar-scanner"
                }
            }
        }

        stage ("Run Unit Test"){
            steps {
                echo "Running Unit Test Cases"
            }
        }
        stage ("Deploy Dev"){
            steps {
                echo "Deploying.....${DEV}"
            }
        }
        stage ("Deploy UAT"){
            steps {
                echo "Deploying.....${UAT}"
            }
        }

        stage ("Deploy PRD"){
            input{
                message "Do you want to proceed for production deployment?"
            }
            steps {
                echo "Deploying.....${PRD}"
            }
        }

    }
}
