echo '${params.HOST}'

pipeline {
    agent any
    environment {
        commiter = sh (script: 'git --no-pager show -s --format=\'%ae\'', returnStdout: true).trim()
        commit_message = sh (script: 'git --no-pager show -s --format=\'%B\'', returnStdout: true).trim()
        short_commit_tag = env.GIT_COMMIT.take(7)
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
                echo "++++++++++++++++++"
                for (element in params) {
                    echo "BLA BLA ${element.key} ${element.value}"
                }
                echo "HOST is ${params.HOST}"
                echo "*${JOB_NAME}* pipeline initiated... |${env.GIT_COMMIT.take(7)}\nCommit Message: ${commit_message}\nAuthor: ${commiter}\nBuild URL: ${env.BUILD_URL}console"
                }
                }
            }
        }
    }
