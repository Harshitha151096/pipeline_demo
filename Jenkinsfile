pipeline{
    agent none
    stages{
        parallel{
            stage('Checkout'){
                agent {label 'ubuntu_slave1'}
                steps{
                    echo 'Checking out...'
                    checkout scmGit(branches: [[name: '*/pipeline_branch']],
                                extensions: [],
                                userRemoteConfigs: [[credentialsId: 'Harshitha',
                                url: 'https://github.com/Harshitha151096/pipeline_demo.git']])
                            }
            }
            stage('Build'){
                agent {label 'ubuntu_slave1'}
                steps{
                        echo 'Building...'
                }
            }
        }
        stage('Test'){
            agent {label 'ubuntu_slave2'}
            steps{
                    echo 'Testing...'
            }
        }
            stage('Deploy'){
                agent {label 'ubuntu_slave2'}
                steps{
                    echo 'Deploying...'
            }
        }
    }   
    
}