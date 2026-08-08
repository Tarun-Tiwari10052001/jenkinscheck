pipeline {
    agent any

    triggers {
        cron('*/5 * * * *')
    }

    stages {
        stage('Schedule') {
            steps {
                echo "SCHEDULE TRIGGERED"
                echo "Branch: ${env.BRANCH_NAME}"
            }
        }
    }
}
