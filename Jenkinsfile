pipeline {
    agent any

    parameters {
        string(name: 'BRANCH_NAME', defaultValue: 'main', description: 'Branch to build')
        choice(name: 'ENVIRONMENT', choices: ['dev', 'staging', 'production'], description: 'Deployment environment')
        booleanParam(name: 'RUN_TESTS', defaultValue: true, description: 'Run tests after build?')
    }
    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out...'
                checkout scmGit(branches: [[name: "*/${params.BRANCH_NAME}"]],
                        extensions: [],
                        userRemoteConfigs: [[credentialsId: 'Harshitha',
                        url: 'https://github.com/Harshitha151096/pipeline_demo.git']])
            }
        }

        stage('Parallel Tasks') {
            parallel {
                stage('Build') {
                    steps {
                        echo 'Building...'
                    }
                }
                stage('Test') {
                    steps {
                        echo 'Testing...'
                    }
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
}
