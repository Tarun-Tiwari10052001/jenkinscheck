pipeline {
    agent any

    triggers {
        GenericTrigger(
            token: 'webhook-test',
            causeString: 'GitHub push',
            printContributedVariables: true,
            printPostContent: false
        )
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
