pipeline {
    agent any

    triggers {
        githubPush()
    }

    stages {
        stage('Checkout Develop Branch') {
            steps {
                dir('/opt/app/develop-code') {
                    git branch: 'develop',
                        url: 'https://github.com/your-org/your-repo.git',
                        credentialsId: 'github-creds'
                }
            }
        }
    }
}
