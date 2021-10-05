pipeline {
    agent any
    environment {
        PRD = "PROD"
        DEV = "DEV"
        UAT = "ACC"
    }
    stages {
        // stage ("Checkout"){
        //    // agent "label_node"
        //     steps{
        //         script {
                   
        //            sh """
        //                 rm -rf java-sample-app
        //                 git clone https://github.com/crazy4devops/java-sample-app.git
        //                 cd java-sample-app
        //                 git checkout dev
        //                 ls -lrt
        //            """
        //         }
        //     }
        // }
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
                // script {
                //     sh "mvn test"

                // }
            }
        }
        stage ("Deploy Dev"){
            steps {
                echo "Deploying.....Dev"
            }
        }
        stage ("Deploy UAT"){
            steps {
                echo "Deploying.....UAT"
            }
        }

        stage ("Deploy PRD"){
            input{
                message "Do you want to proceed for production deployment?"
            }
            steps {
                echo "Deploying.....PRD"
            }
        }

    }
}
