pipeline{
    agent none
    stages{
        stage('Checkout'){
            agent {label 'ubuntu_slave2'}
            steps{
                echo 'Checking out...'
                checkout scmGit(branches: [[name: '*/main']],
                            extensions: [],
                            userRemoteConfigs: [[credentialsId: 'Harshitha',
                            url: 'https://github.com/Harshitha151096/pipeline_demo.git']])
                        }
       }
        stage('Build'){
            agent {label 'ubuntu_slave2'}
            steps{
                    echo 'Building...'
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