echo '${params.HOST}'

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
                //for (element in params) {
                    // testing:
                //    echo "${element.key} ${element.value}"
                //}
                script {
                params.keySet().each {
                    echo "The value of the ${it} parameter is: ${params[it]}"
                }
                echo "HOST is ${params.HOST}"
                }
                }
            }
        }
    }
