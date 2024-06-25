pipeline {
    agent {
                label 'AGENT-1'
    }
     options {
        timeout(time: 30, unit: 'MINUTES') 
        disableConcurrentBuilds()
        ansiColor('xterm')
    }

     parameters {
        string(name: 'appVersion', defaultValue: '1.0.0', description: 'What is the application version?')

     environment{
        def appVersion = ''
        nexusUrl = 'nexus.daws304.online:8081'
     }
    stages {
        stage('print the version'){
            steps{
                script{
                echo "application version: ${params.appVersion}"
                }
        }
        }
    }

      post {
        always {
            echo 'I will always say Hello Again!'
            deleteDir()
        }
        success {
            echo 'I will run when the pipeline is success!'
        }
        failure {
            echo 'I will run when the pipeline is failure!'
        }
    }
}




