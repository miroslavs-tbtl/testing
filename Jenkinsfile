pipeline {
    agent any
    environment {
        commiter = sh (script: 'git --no-pager show -s --format=\'%ae\'', returnStdout: true).trim()
        commit_message = sh (script: 'git --no-pager show -s --format=\'%B\'', returnStdout: true).trim()
    }
    stages {

        stage('Test Deploy') {
            steps {
                echo 'Sending Slack notification...'
            for (entry in params) {
              echo '${params.HOST}'
             }
                }
            }
        }
    }
