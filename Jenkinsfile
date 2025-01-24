pipeline {
    agent any
    tools {
        nodejs 'yarn'
    }

    stages {
        stage('install') {
            steps {
                sh 'yarn'
            }
        }

        stage('build') {
            steps {
                sh 'yarn build'
            }
        }

        stage('E2E') {
            steps {
                sh 'yarn e2e'
            }
        }
    }
    post  {
        always {
            junit '**/reports/**/*.xml'
        }
    }
}
