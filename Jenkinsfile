pipeline {
    agent any
    stages {
        stage('cleanup') {
            steps {
                sh 'echo "This is a test"'
            }
        }
    }
    post { 
       success {
           slackSend color: 'good', channel: 'web-buildsvbout-deployments', message: "The Landing cleanup pipeline job has succeeded for ${params.domain}!"
       }
       failure {
           slackSend color: '#FF0000', channel: 'vbout-deployments', message: "The Landing cleanup pipeline job has failed for ${params.domain}!"
       }
    }
}
