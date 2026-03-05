pipeline{
    agent any 
    stages{
        stage('Checkout'){
            steps{
                echo 'Checking out...'
                checkout scmGit(branches: [[name: '*/main']],
                            extensions: [],
                            userRemoteConfigs: [[credentialsId: 'Harshitha',
                            url: 'https://github.com/Harshitha151096/pipeline_demo.git']])
                        }
       }
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
            stage('Deploy'){
                steps{
                    echo 'Deploying...'
            }
        }
    }   
    
}