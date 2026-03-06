pipeline{
    agent any
    stages{
        stage('Checkout'){
            steps {
                echo 'Checking out...'
                checkout scmGit(branches: [[name: '*/pipeline_branch']],
                        extensions: [],
                        userRemoteConfigs: [[credentialsId: 'Harshitha',
                        url: 'https://github.com/Harshitha151096/pipeline_demo.git']])
            }
        }
        stage('Build and test'){

            parallel{
                    stage('Build'){
                    steps{
                           echo 'Building...'
                    }
                    }
                    stage('Test'){
                            steps{
                            echo 'Testing...'
                            }
                    }
            }
            stage('Deploy'){
                steps{
                      echo 'Deploying...'
                }
            }
        }
    }
}