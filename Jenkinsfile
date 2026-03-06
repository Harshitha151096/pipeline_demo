pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out...'
                checkout scmGit(branches: [[name: '*/pipeline_branch']],
                        extensions: [],
                        userRemoteConfigs: [[credentialsId: 'Harshitha',
                        url: 'https://github.com/Harshitha151096/pipeline_demo.git']])
            }
        }
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
        stage('Parallel Tasks') {
            parallel {
                stage('Unit Tests') {
                    steps {
                        echo 'Running unit tests...'
                        // run your unit tests commands here
                    }
                }
                stage('Linting') {
                    steps {
                        echo 'Running linting...'
                        // run your linting commands here
                    }
                }
                stage('Security Scan') {
                    steps {
                        echo 'Running security scan...'
                        // run your security scan commands here
                    }
                }
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
}
