pipeline {
    agent any

    triggers {
        githubPush()
    }

    stages {
        stage('Webhook Push') {
            steps {
                echo "PUSH TRIGGERED"
                echo "Branch: ${env.BRANCH_NAME}"
            }
        }
    }
}
