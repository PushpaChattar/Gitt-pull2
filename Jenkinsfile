pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Check out the code from your GitHub repository
                checkout([$class: 'GitSCM', 
                    branches: [[name: 'main']], 
                    doGenerateSubmoduleConfigurations: false, 
                    extensions: [], 
                    submoduleCfg: [], 
                    userRemoteConfigs: [[url: 'https://github.com/PushpaChattar/Gitt-pull2.git']]
                ])
            }
        }

        stage('Deploy to Apache') {
            steps {
                // Copy the code to the Apache document root directory
                bat script: '''
                    xcopy /s /e /y "E:\Git pull2" "C:\\Apache24\\htdocs"
                '''
            }
        }
    }

    // post {
    //     success {
    //         // Perform any additional actions on success
    //     }
    //     failure {
    //         // Perform any actions in case of failure
    //     }
    // }
}
